# Setting up the Giza Node server and the ZLUX Secure Services address space on z/OS

Setting up the Giza Node server and the ZLUX Secure Services address space on z/OS is a multi-step installation and configuration process.

The zLUX archive is distributed as a pax archive. When you unpack the archive, both the Giza Node server and the ZLUX Secure Services \(ZSS\) are installed on the z/OS host.

1.   If you have not already done so, follow the procedures in these prerequisite sections: 
    -   [Verifying that your system meets the software requirements](mvd-verifysystemswreqs.md)
    -   [Confirming that Node.js is installed](mvd-instconfirmnodejsinstalled.md)
    -   [Verifying port number availability](mvd-instverifyportnumavailable.md)
 
2. To obtain the installation media, follow the instructions in [Obtain the Project Giza installation media](installing.md).
3. Navigate to the scripts/zlux directory and run zlux-install-script.sh


4.   If you need to specify a port number other than the default \(8542\) for `zssPort` in zluxserver.json, complete these steps: 
    1.   Navigate to the zlux-example-server/config directory: cd zlux-example-server/config. 
    2.   Edit zluxserver.json to assign the appropriate number to `zssPort`. 
    3.   Save the changes to zluxserver.json. 
5.   Upon startup, the Giza Node server loads the zluxserver.json configuration file \(from zlux-example-server/deploy/instance/ZLUX/serverConfig/zluxserver.json\). The JSON configuration file adheres to a specific structure, as shown in the following figure:

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

    -   **Port field for the http field of the node object**

        Required if you intend to access the ZLUX Secure Services address space through unencrypted HTTP. Specify a port number that is available on your system.

    -   **Port field for the https field of the node object**

        Specify the following ports to connect to the node server. Specify a port number that is available on your system. Requires `keys` and `certificates`:

        -   **`keys`**

            The location of the private key file relative to the location of the JSON configuration file. The code page of this file should be the native code page of the host \(EBCDIC for z/OS\).

        -   **`certificates`**

            The location of the certificate file relative to the location of the JSON configuration file. The code page of this file should be the native code page of the host \(EBCDIC for z/OS\).

    **Note:** Currently, the ZLUX Secure Services address space configuration JSON file at zlux-example-server/config/zluxserver.json contains an example node configuration, so you can refer to one file for both the ZLUX Secure Services address space and the Giza Node server.
    
    To update the server configuration, run zlux-example-server/build/deploy.sh


6.   Start the zLUX servers: 

    -   If you are running the Giza Node server on z/OS, complete these steps:
        1.  Navigate to zlux-example-server/bin.
        2.  Run nodeServer.sh:

            ```
            nodeServer.sh
            ```

            The ZLUX Secure Services address space \(zssServer.sh\) starts automatically.

    -   If you are running the Giza Node server on Windows, complete these steps:
        1.  Navigate to zlux-example-server\\bin.
        2.  Run nodeServer.bat:

            ```
            nodeServer.bat --hostServer=serveraddress --hostPort=portnumber
            ```

            where:

            -   serveraddress is the address of the z/OS system where Node.js is running.
            -   portnumber is the port number that you configured for `zssPort` in step 5 of this procedure.
    
    **Note:** The ZLUX Secure Services address space log output is very verbose. Redirecting the output is not generally recommended. If you require a log file, restart the ZLUX Secure Services address space and redirect the output to a file of your choosing. Because log output can quickly fill up a file system, it is not recommended that you leave the ZLUX Secure Services address space running for long periods of time with the output directed to a file.

Go on to [Opening the MVD in a browser](mvd-instopendesktopbrowser.md).
