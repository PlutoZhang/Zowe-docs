The file zoe-install.yaml in the /install folder contains values used during the install

The values supplied are defaults can be modified by editing the zoe-install.yaml file
 ```
install:
    rootDir=/usr/lpp/zoe
explorer-server:
    httpPort=7080
    httpsPort=7443
zlux-server:
    httpPort=8543
    httpsPort=8544
    zssPort=8542
 ```
 
1. install

The rootDir value is where the install will put the zoe runtime files into.  The default is /usr/lpp/zoe, however the user running the install may have insufficient priveldges, in which case another folder such as  /u/myuser/zoe can be used to complete the install.

2. explorer-server

The httpPort and the httpsPort are used by the explorer-server to access the MVS-Explorer, USS-Explorer and JES-Explorer as well as the Swagger Hub serving the REST APIs.

3. zlux-server

The httpPort and the httpsPort are used by the zlux-server to access the Virtual Desktop
The zssPort is used for the z secure services server that is not accessed by the end user, but must have its own port that the zLux server can communicate with