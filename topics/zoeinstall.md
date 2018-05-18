# Installing the Zoe runtime on z/OS

1. Navigate to the directory where the install archive was unpacked into.  Locate the `/install` directory.

    ```
         /install
            /zoe-install.sh
            /zoe-install.yaml

    ```

2. Review zoe-install.yaml which contains the following properties.

    - install:rootDir is the directory that Zoe will be installed into to create a Zoe runtime.  The default directory is `~/zoe/0.8.1`. The user's home directory is used as a default value to help ensure that the installing user has permission to create the directories needed for the install.  If the Zoe runtime is going to be used by different users it may be more appropriate to use another directory, such as `/var/zoe/v.r.m`.

       You may run the install multiple times with different values in the `zoe-install.yaml` file to create separate installations of the Zoe runtime.  The directory that Zoe is installed into must be empty. The install script will exit if the directory is not empty and create the directory if it does not exist.

    - explorer-server has two ports, one for HTTP and one for HTTPs.  The liberty server is used for the explorer-ui components.

    - zlux-server has three ports: the HTTP and HTTPs ports that are used by the zLUX window manager server, and the port that is used by the ZSS server.

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

    If all of these port values are OK then you do not need to change them.  These ports must not already being used for the Zoe runtime servers to be able to allocate them.  

    To determine which ports are not available, follow these steps:

    - To display a list of ports that are in use, issue the following command:

    ```
    TSO NETSTAT to display
    ```

    - To display a list of reserved ports, issue the following command:

    ```
    TSO NETSTAT PORTLIST
    ```  

    The zoe-install.yaml also contains the telnet and SSH port with defaults of 23 and 22.  If your z/OS LPAR is using different ports, edit the values.  This is to allow the TN3270 terminal desktop app to connect as well as the VT terminal desktop app.  Unlike the ports needed by the Zoe runtime for its zLUX and explorer server which must be unused, the terminal ports are expected to be be in use.

    ```
    # Ports for the TN3270 and the VT terminal to connect to    
    terminals:
        sshPort=22
        telnetPort=23
    ```

2. Execute the zoe-install.sh script

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

    When the `zoe-install.sh` script runs, it performs a number of steps broken down into sections. These are covered more in the section  [Troubleshooting installing the Zoe runtime](topics/zoeinstalltroubleshoot.md).
