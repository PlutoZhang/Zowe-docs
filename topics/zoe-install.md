Navigate to the /config directory where the install archive was unpaxed.  Locate the /config folder 

```
     /install
        /zoe-install.sh
        /zoe-install.yaml

```

1. Review zoe-install.yaml which contains five properties

install:rootDir is the directory that zoe will be installed into to create a zoe runtime.  The default is /usr/lpp/zoe however you can change this to a different folder.  You may run the install multiple times with different values in the zoe-install.yaml file to create separate installations of the zoe runtime.  

liberty-server has two ports, one for http and one for https.  The libery-server is used for the explorer-ui components.

node-server has three ports, one for its http and https ports used by the zLUX window manager server, as well as the port that is used by the zss server.

If all of these values are OK then you do not need to change them.

```
install:
  rootDir=/usr/lpp/zoe

# http and https ports for the liberty server
liberty-server:
  httpPort=7080
  httpsPort=7443

# http and https ports for the node server
node-server:
  httpPort=8543
  httpsPort=8544
  zssPort=8542
```

2. Execute the zoe-install.sh script

Navigate to the /install directory and execute the script zoe-install.sh.

During the install of the Liberty explorer-server group ownership of files is altered to be IZUADMIN.  This means that the user running the install must be a member of the IZUADMIN group or have super-user authority.  

The script uses a number of variables defined in the file zoe-install.yaml to determine the directory that the zoe runtime should be installed into, as well as ports numbers to be used.

As the zoe-install.sh script runs it performs a number of steps broken down into sections.  These are covered more in the section "Troubleshooting the install process".  

At the end of the install a zFS file ZOESVR is created in the /jcl folder where the runtime was successfully installed into.  This file needs to be part of the PROCLIB for the Zoe runtime to be executed as a started task.  The install script will attempt to add ZOESVR to the PROCLIB however this is dependent on the user's priviledges so this may require a user with elevated priviledges to perform this step.

There are two ways in which Zoe can be started.

One is as a Unix process from a unix shell.  

To perform this navigate to the folder /scripts in the location where the Zoe runtime was installed into and execute

zoestart.sh

The second way in which Zoe can be started is as a started task.  To perform this launch SDSF and issue the operator command /S ZOESVR.  To stop the Zoe runtime issue the operator command /C ZOESVR.  

-   **[Locating system wide environment variables](../topics/zoeinit.md)**
-   **[Preparing the install environment](../topics/zoeparse.md)**
-   **[Installing the Zoe runtime](../topics/zoeinstall.md)**




