# Setting up the NODE.js server and the ZLUX Secure Services address space on z/OS

Setting up the Project Giza Node.js server and the ZLUX Secure Services address space on z/OS is a multi-step installation and configuration process.

The zLUX archive is distributed as a pax archive. When you unpack the archive, both the Project Giza Node.js server and the ZLUX Secure Services \(ZSS\) are installed on the z/OS host.

1.   If you have not already done so, follow the procedures in these prerequisite sections: 
    -   [Verifying that your system meets the software requirements](mvd-verifysystemswreqs.md#)
    -   [Confirming that Node.js is installed](mvd-instconfirmnodejsinstalled.md#)
    -   [Verifying port number availability](mvd-instverifyportnumavailable.md#)
2.   Use the cd command to navigate to the directory in which you want to restore the zLUX archive, or create a new directory for that purpose and navigate to the new directory. 
3.   Execute the pax command with these specific options to restore the zLUX archive under the current directory: 

    pax -r -px -f archive-location/zLUX.pax

    where:

    -   `-p` specifies which file characteristics you want to restore.
    -   `x` preserves extended attributes that were set originally by the extattr command.
    When you run the ls command in the directory, you see the directory contents:

    ```
    README.md
    sample-app/
    tn3270-ng2/
    zlux-app-manager/
    zlux-example-server/
    zlux-ng2/
    zlux-platform/
    zlux-proxy-server/
    zlux-shared/
    zos-subsystems/
    ```

4.   Verify that the extended attributes were preserved for the file zlux-example-server/bin/zssServer: 

    ```
    $ cd zlux-example-server/bin
    $ ls -E
    total 5824
    -rw-rw-r-- --s-  1 TSSPG   TSUSER   177 Jan 11 13:11 nodeSever.bat
    -rwxrwxr-x --s-  1 TSSPG   TSUSER   538 Jan 11 13:11 nodeServer.sh
    -rwxrwxr-x aps-  1 TSSPG   TSUSER   2945024 Jan 31 19:26 zssServer
    -rwxrwxr-x a-s-  1 TSSPG   TSUSER   538 Jan 11 13:11 zssSever.sh
    ```

    If the `a` attribute is absent, you lack sufficient authority on the z/OS system. To correct this problem, have a user who has sufficient authority run the extattr command to add the attribute: extattr +a zssServer 

5.   If you need to specify a port number other than the default \(8542\) for `zssPort` in zluxserver.json, complete these steps: 
    1.   Navigate to the zlux-example-server/config directory: cd zlux-example-server/config. 
    2.   Edit zluxserver.json to assign the appropriate number to `zssPort`. 
    3.   Save the changes to zluxserver.json. 
6.   Upon startup, the Project Giza Node.js server loads the zluxserver.json configuration file \(from zlux-example-server/deploy/instance/ZLUX/serverConfig/zluxserver.json\). The JSON configuration file adheres to a specific structure, as shown in the following figure:

    ```
      "node": {
        "http": {
          **"port": 8543**
        },
        "https": {
          **"port": 8544**,
          //pfx (string), keys, certificates, certificateAuthorities, and 
    certificateRevocationLists are all valid here.
          **"keys"**: ["../deploy/product/ZLUX/serverConfig/server.key"],
          **"certificates"**: ["../deploy/product/ZLUX/serverConfig/server.cert"]
          }
        },
        "childProcesses": [
          {
            "path": "../bin/zssServer.sh"
          }
        ]
      },
    ```

    Note the following about specifying values in the JSON configuration file:

    -   **Port field for the http filed of the node object**

        Required if you intend to access the ZLUX Secure Services address space through unencrypted HTTP. Specify a port number that is available on your system.

    -   **Port field for the https field of the node object**

        Required if you intend to access the ZLUX Secure Services address space through encrypted HTTPS. Specify a port number that is available on your system. Requires `keys` and `certificates`:

        -   **`keys`**

            The location of the private key file relative to the location of the JSON configuration file. The code page of this file should be the native code page of the host \(EBCDIC for z/OS\).

        -   **`certificates`**

            The location of the certificate file relative to the location of the JSON configuration file. The code page of this file should be the native code page of the host \(EBCDIC for z/OS\).

    **Note:** Currently, the ZLUX Secure Services address space configuration JSON file at zlux-example-server/config/zluxserver.json contains an example node configuration, so you can refer to one file for both the ZLUX Secure Services address space and the Project Giza Node.js server.

7.   Start the Project Giza servers: 

    -   If you are running the Project Giza Node.js server on z/OS, complete these steps:
        1.  Navigate to zlux-example-server/bin.
        2.  Run nodeServer.sh:

            ```
            nodeServer.sh
            ```

            The ZLUX Secure Services address space \(zssServer.sh\) starts automatically.

    -   If you are running the Project Giza Node.js server on Windows, complete these steps:
        1.  Navigate to zlux-example-server\\bin.
        2.  Run nodeServer.bat:

            ```
            nodeServer.bat --hostServer=serveraddress --hostPort=portnumber
            ```

            where:

            -   serveraddress is the address of the z/OS system where Node.js is running.
            -   portnumber is the port number that you configured for `zssPort` in step 5 of this procedure.
    **Note:** The ZLUX Secure Services address space log output is very verbose. Redirecting the output is not generally recommended. If you require a log file, restart the ZLUX Secure Services address space and redirect the output to a file of your choosing. Because log output can quickly fill up a file system, it is not recommended that you leave the ZLUX Secure Services address space running for long periods of time with the output directed to a file.

Go on to [Opening the Project Giza desktop in a browser](mvd-instopendesktopbrowser.md).
