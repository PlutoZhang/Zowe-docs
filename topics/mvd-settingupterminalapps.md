# Setting up terminal application plug-ins

Complete the following optional steps to configure the terminal application plug-ins.

## Setting up the TN3270 mainframe terminal application plug-in
Complete the following optional step to define the best default connection to open.

`_defaultTN3270.json` is a file in `zlux-example-server/build`, which is deployed during setup. Within this file, you can specify parameters to instruct the terminal to connect to a system by default.

Specify the following parameters to configure the terminal connection:
    
      "host": <hostname>
      "port": <port>
      “security”: {
      type: <”telnet” or “tls”>
    }
    
## Setting up the VT Terminal application plug-in
Complete the following optional step to define the best default connection to open.

`_defaultVT.json` is a file in `zlux-example-server/build`, which is deployed during setup. Within this file, you can specify parameters to instruct the terminal to connect to a system by default.

Specify the following parameters to configure the terminal connection:
 
    “host”:<hostname>
    “port”:<port>
    “security”: {
      type: <”telnet” or “ssh”>
    }