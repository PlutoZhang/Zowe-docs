# Setting up the Giza Node server and the zLUX Secure Services address space on z/OS

The zLUX archive is distributed as a PAX archive. When you unpack the archive, both the Giza Node server and the zLUX Secure Services \(ZSS\) are installed on the z/OS host.

1.   If you have not already done so, complete the procedures in the prerequisite sections: 
    -   [Verifying that your system meets the software requirements](mvd-verifysystemswreqs.md)
    -   [Confirming that Node.js is installed](mvd-instconfirmnodejsinstalled.md)
    -   [Verifying port number availability](mvd-instverifyportnumavailable.md)
 
2. To obtain the installation media, follow the instructions in [Obtain the Project Giza installation media](installing.md).
3. Navigate to the `scripts/zlux` subdirectory of the Project Giza contents directory (where you unpacked the Project Giza PAX file) and issue the following command: 
```
   zlux-install-script.sh
```
4.   Upon startup, the Giza Node server loads the `zluxserver.json` configuration file \(from `zlux-example-server/deploy/instance/ZLUX/serverConfig/zluxserver.json\`). The JSON configuration file adheres to a specific structure, as shown in the following figure:

  ```
      "node": {
        "http": {
          "port": 8543
        },
        "https": {
          "port": 8544,
          //pfx (string), keys, certificates, certificateAuthorities, and 
    certificateRevocationLists are all valid here.
          "keys": ["../deploy/product/ZLUX/serverConfig/server.key"],
          "certificates": ["../deploy/product/ZLUX/serverConfig/server.cert"]
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

     Required if you intend to access the zLUX Secure Services address space through unencrypted HTTP. Specify a port number that is available on your system.

 -   **Port field for the https field of the node object**

     Required if you intend to access the zLUX Secure Services address space through encrypted HTTPS. Specify a port number that is available on your system. Requires `keys` and `certificates`.

     **Note:** Currently, the zLUX Secure Services address space configuration JSON file at `zlux-example-server/config/zluxserver.json` contains an example node configuration, so you can refer to one file for both the zLUX Secure Services address space and the Giza Node server.

5.  (Optional.) Set up the terminal application plug-ins. For more information, see [Setting up terminal application plug-ins](mvd-settingupterminalapps.md).    

6. To update the server configuration, issue the following command:

```
  zlux-example-server/build/deploy.sh
```

     
Start the server as described in [Starting the zLUX server](mvd-startzluxserver.md).
