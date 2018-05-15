# Stop and start Zoe runtime

Zoe has two runtime components on z/OS, the explorer server and the zLUX server

1. Starting the explorer server

Run the PROCLIB ZOESVR by issusing the operator command in SDSF

```
/S ZOESVR.
```

This will bring up the explorer server.  To test whether the server is active open the URL
https://<hostname>:7443/ui

The port number 7443 is the default port and can be overridden through the zoe-install.yaml before the zoe-install.sh script is run.  

To stop the Zoe runtime issue the operator command:

```
/C ZOESVR.  
```

4. Start the zLux server

Navigate to the folder `/zlux-example-server/bin` in the location where the Zoe runtime was installed into and execute the script nodeServer.sh.

To run the zLUX server in the background to the current shell append & on the command, and to ensure the zLUX server remains active once the shell disconnects prepend with nohop

```
nohop nodeServer.sh &
```
