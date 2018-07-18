# Installing the Zoe runtime on z/OS

To install API Mediation Layer, zLux, and explorer server, you install the Zoe runtime on z/OS.

**Follow these steps:**

1. Navigate to the directory where the install archive was unpacked.  Locate the `/install` directory.

    ```
         /install
            /zoe-install.sh
            /zoe-install.yaml

    ```

2. Review the `zoe-install.yaml` file which contains the following properties.

    - `install:rootDir` is the directory that Zoe will be installed into to create a Zoe runtime. The default directory is `~/zoe/0.8.3`. The user's home directory is the default value to ensure that the installing user has permission to create the directories that are required for the install. If the Zoe runtime will be maintained by multiple users it might be more appropriate to use another directory, such as `/var/zoe/v.r.m`.

        You can run the installation process multiple times with different values in the `zoe-install.yaml` file to create separate installations of the Zoe runtime. The directory that Zoe is installed into must be empty. The install script exits if the directory is not empty and creates the directory if it does not exist.

    - API Mediation Layer has three ports - one HTTPS port for each micro-service. 
    
    - Explorer-server has two ports - one for HTTP and one for HTTPS.  The liberty server is used for the explorer-ui components.

    - zLux-server has three ports: the HTTP and HTTPS ports that are used by the zLUX window manager server, and the port that is used by the ZSS server.



    ```yaml
    install:
     rootDir=/var/zoe/0.8.3
     
    api-mediation:
      catalogHttpsPort=7552
      discoveryHttpsPort=7553
      gatewayHttpsPort=7554 

    explorer-server:
      httpPort=7080
      httpsPort=7443

    # http and https ports for the node server
    zlux-server:
      httpPort=8543
      httpsPort=8544
      zssPort=8542
    ```

    If all of the default port values are acceptable then you do not need to change them. The ports must not be in use for the Zoe runtime servers to be able to allocate them.  

    To determine which ports are not available, follow these steps:

    - To display a list of ports that are in use, issue the following command:

    ```
    TSO NETSTAT
    ```

    - To display a list of reserved ports, issue the following command:

    ```
    TSO NETSTAT PORTLIST
    ```  

    The zoe-install.yaml also contains the telnet and SSH port with defaults of 23 and 22.  If your z/OS LPAR is using different ports, edit the values. This is to allow the TN3270 terminal desktop app to connect as well as the VT terminal desktop app.  Unlike the ports needed by the Zoe runtime for its zLUX and explorer server which must be unused, the terminal ports are expected to be in use.

    ```
    # Ports for the TN3270 and the VT terminal to connect to    
    terminals:
        sshPort=22
        telnetPort=23
    ```

3. Execute the zoe-install.sh script.

    With the current directory being the `/install` directory, execute the script `zoe-install.sh` by issuing the following command:

    ```
    zoe-install.sh
    ```
    You might receive the following error that the file cannot be executed.

    ```
    zoe-install.sh: cannot execute
    ```
    The error is due to that the install script does not have execute permission. To add execute permission, issue the following command:

    ```
    chmod u+x zoe-install.sh.
    ```

    When the `zoe-install.sh` script runs, it performs a number of steps broken down into sections. These are covered more in the section [Troubleshooting installing the Zoe runtime](zoeinstalltroubleshoot.md).
