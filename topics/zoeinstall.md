# Installing the Zoe runtime on z/OS

1. Navigate to the `/config` directory where the install archive was unpacked.  Locate the `/install` directory.

    ```
         /install
            /zoe-install.sh
            /zoe-install.yaml

    ```

2. Review zoe-install.yaml which contains the following properties.

    - install:rootDir is the directory that Zoe will be installed into to create a Zoe runtime.  The default directory is `/var/zoe/0.8.1`. However, you can change the directory to a different folder.  You may run the install multiple times with different values in the `zoe-install.yaml` file to create separate installations of the Zoe runtime.  The directory that Zoe is installed into must be empty. The install script will exit if the directory is not empty and create the directory if it does not exist.

    - explorer-server has two ports, one for HTTP and one for HTTPs.  The liberty server is used for the explorer-ui components.

    - zlux-server has three ports: the HTTP and HTTPs ports that are used by the zLUX window manager server, and the port that is used by the ZSS server.

    If all of these values are OK then you do not need to change them.  

    ```
    install:
     rootDir=/var/zoe/0.8.1

    explorer-server:
      httpPort=7080
      httpsPort=7443

    # http and https ports for the node server
    zlux-server:
      httpPort=8543
      httpsPort=8544
      zssPort=8542
    ```

2. Execute the zoe-install.sh script

    Navigate to the `/install` directory and execute the script `zoe-install.sh` by issuing the following command:

    ```
    .zoe-install.sh
    ```
    You might receive the following error that the file cannot be executed.

    ```
    zoe-install.sh: cannot execute
    ```
    The error is due to that the install script does not have execute permission. To add execute permission, issue the following command:

    ```
    chmod u+u zoe-install.sh.
    ```

    During the installation of the Liberty explorer server, group ownership of files is altered to be IZUADMIN.  This means that the user running the install must be a member of the IZUADMIN group or have super-user authority.  

    The script uses a number of variables defined in the file `zoe-install.yaml` to determine the directory that the Zoe runtime should be installed into, as well as ports numbers to be used.

    When the `zoe-install.sh` script runs, it performs a number of steps broken down into sections. These are covered more in the section "Troubleshooting the install process".  

    At the end of the installation, a zFS file ZOESVR is created in the `/jcl` folder where the runtime was successfully installed into. This file needs to be part of the PROCLIB for the Zoe runtime to be executed as a started task. The install script will attempt to add ZOESVR to the PROCLIB, however, this is dependent on the user's privileges so this might require a user with elevated privileges to perform this step.

3. Start the Zoe runtime as a started task.

    Running Zoe as a started task is the preferred way to start and stop Zoe.  

    To start Zoe as a started task, launch SDSF and issue the operator command:

    ```
    /S ZOESVR.
    ```

    To stop the Zoe runtime issue the operator command:

    ```
    /C ZOESVR.  
    ```

4. Start the Zoe runtime as a Unix process.

    To perform this, navigate to the folder `/scripts` in the location where the Zoe runtime was installed into and execute the script:

    ```
    zoestart.sh
    ```

    To end the Zoe runtime execute the script:

    ```
    zoestop.sh
    ```
