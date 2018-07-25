# Troubleshooting installing the Zoe runtime

1.  Environment variables

    To prepare the environment for the Zoe runtime, a number of ZFS folders need to be located for prerequisites on the platform that Zoe needs in order to operate. These can be set as environment variables before the script is run.  If the environment variables are not set, the install script will attempt to locate default values.

     - `ZOE_ZOSMF_PATH`: The path where z/OSMF is installed.  Defaults to `/usr/lpp/zosmf/lib/defaults/servers/zosmfServer`
     - `ZOE_JAVA_HOME`:  The path where 64 bit Java 8 or later is installed.  Defaults to `/usr/lpp/java/J8.0_64`
     - `ZOE_EXPLORER_HOST`: The IP address of where the explorer servers are launched from.  Defaults to running `hostname -c`

    The first time the script is run if it has to locate any of the environment variables, the script will add lines to the current user's home directory `.profile` file to set the variables.  This ensures that the next time the same user runs the install script, the previous values will be used.

     **Note**: If you wish to set the environment variables for all users, add the lines to assign the variables and their values to the file `/etc/.profile`.  

    If the environment variables for `ZOE_ZOSMF_PATH`, `ZOE_JAVA_HOME` are not set and the install script cannot determine a default location, the install script will prompt for their location.  The install script will not continue unless valid locations are provided.  

2. Expanding the PAX files

    The install script will create the Zoe runtime directory structure using the  `install:rootDir ` value in the  `zoe-install.yaml` file.  The runtime components of the Zoe server are then unpaxed into the directory that contains a number of directories and files that make up the Zoe runtime.

    If the expand of the PAX files is successful, the install script will report that it ran its install step to completion.

3. Changing Unix permissions

    After the install script has laid down the contents of the Zoe runtime into the `rootDir`, the next step is to set the file and directory permissions correctly to allow the Zoe runtime servers to start and operate successfully.

    The install process will execute the file `scripts/zoe-runtime-authorize.sh` in the Zoe runtime directory.  If the script is successful, the result will be reported.  If for any reason the script fails to run because of insufficient authority by the user running the install, the install process will report the errors.  A user with sufficient authority should then run the `zoe-runtime-authorize.sh`.  If you attempt to start the Zoe runtime servers without the `zoe-runtime-authorize.sh` having successfully completed, the results are unpredictable and Zoe runtime startup or runtime errors will occur.  

4. Creating the PROCLIB member to run the Zoe runtime

    **Note:**  The name of the PROCLIB member may vary depending on the standards in place at each z/OS site, however for this documentation we assume that the PROCLIB member is called `ZOESVR`.

    At the end of the installation, a Unix file `ZOESVR.jcl` is created under the directory where the runtime was installed into, `$INSTALL_DIR/files/templates`. The contents of this file need to be tailored and placed in a JCL member of the PROCLIB concatenation for the Zoe runtime to be executed as a started task.  The install script does this automatically, trying data sets `USER.PROCLIB`, other PROCLIB data sets found in the PROCLIB concatenation and finally `SYS1.PROCLIB`.  

    If this succeeds, you will see a message like the following one:

     ```PROC ZOESVR placed in USER.PROCLIB```

    Otherwise you will see messages beginning with the following information:  

     ```Failed to put ZOESVR.JCL in a PROCLIB dataset.```

    In this case, you need to copy the PROC manually. The TSO `oget` command can be used to copy the `ZOESVR.jcl` file to the preferred PROCLIB.  

     ```oget '$INSTALL_DIR/files/templates/ZOESVR.jcl' 'MY.USER.PROCLIB(ZOESVR)'```

    You can place the PROC in any PROCLIB data set in the PROCLIB concatenation, but some data sets such as `SYS1.PROCLIB` may be restricted, depending on the permission of the user.  

    You can tailor the JCL at this line

      ```//ZOESVR   PROC SRVRPATH='/zoe/install/path/explorer-server'```

    to replace the `/zoe/install/path` with the location of the Zoe runtime directory that contains the explorer server.  Otherwise you must specify that path on the START command when you start Zoe in SDSF:

      ```/S ZOESVR,SRVRPATH='$ZOE_ROOT_DIR/explorer-server'```

5. Adding RACF authorizations for Zoe

    To define RACF authorizations for Zoe, the following steps are required:

     1. Define the PROC named ZOESVR to be a started task.

        ```
        RDEFINE STARTED ZOESVR.* UACC(NONE) STDATA(USER(IZUSVR) GROUP(IZUADMIN) PRIVILEGED(NO) TRUSTED(NO) TRACE(YES))
        
        SETROPTS REFRESH RACLIST(STARTED)
        ```

     2. Add the user who is performing the install to the IZUADMIN group.  

        ```CONNECT (userid) GROUP(IZUADMIN)```
        
     **Note**: If you use ACF2 or Top Secret instead of RACF, to set the ZOESVR to use the IZUSVR user ID, issue the following commands: 

      - For ACF2  

         ```
         SET CONTROL(GSO)
         INSERT STC.ZOESVR LOGONID(ZIUSVR) GROUP(IZUADMIN) STCID(ZOESVR)
         F ACF2,REFRESH(STC)
         ```
      - For Top Secret

         ```TSS ADDTO(STC) PROCNAME(ZOESVR) ACID(IZUSVR)```    
