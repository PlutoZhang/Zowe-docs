# Starting and stopping the Zoe runtime

Zoe has two runtime components on z/OS, the explorer server and the zLUX server.

**Starting the explorer server**

To start the explorer server, run the PROCLIB ZOESVR by issusing the operator command in SDSF.

```
/S ZOESVR.
```

To test whether the explorer server is active, open the URL https://<hostname>:7443/ui.

The port number 7443 is the default port and can be overridden through the zoe-install.yaml before the zoe-install.sh script is run.  

**Starting the zLux server**

Navigate to the folder `/zlux-example-server/bin` in the location where the Zoe runtime was installed into and execute the script nodeServer.sh.

To run the zLUX server in the background to the current shell, append `&` to the command. To ensure that the zLUX server remains active once the shell disconnects, prepend the command with `nohop`.

```
nohop nodeServer.sh &
```

**Stopping the Zoe runtime**

To stop the Zoe runtime, issue the following operator command:

```
/C ZOESVR.  
```


