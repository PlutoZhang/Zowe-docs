# Setting up terminal application plug-ins

Follow these optional steps to configure the default connection to open for the terminal application plug-ins.

## Setting up the TN3270 mainframe terminal application plug-in

`_defaultTN3270.json` is a file in `tn3270-ng2/`, which is deployed during setup. Within this file, you can specify the following parameters to configure the terminal connection:
    
      "host": <hostname>
      "port": <port>
      “security”: {
      type: <”telnet” or “tls”>
    }
    
## Setting up the VT Terminal application plug-in

`_defaultVT.json` is a file in `vt-ng2/`, which is deployed during setup. Within this file, you can specify the following parameters to configure the terminal connection:
 
    “host”:<hostname>
    “port”:<port>
    “security”: {
      type: <”telnet” or “ssh”>
    }