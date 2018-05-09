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

Navigate to the /install directory and execute the script zoe-install.sh

The script uses a number of variables defined in the file zoe-install.yaml to determine the directory that the zoe runtime should be installed into, as well as ports numbers to be used.

As the zoe-install.sh script runs it performs a number of steps broken down into sections. 

-   **[Locating system wide environment variables](../topics/zoeinit.md)**
-   **[Preparing the install environment](../topics/zoeparse.md)**
-   **[Installing the Zoe runtime](../topics/zoeinstall.md)**




