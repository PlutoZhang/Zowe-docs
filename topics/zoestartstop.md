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
nohup nodeServer.sh &
```

**Stopping the explorer server**

To stop the Zoe runtime, issue the following operator command:

```
/C ZOESVR.  
```

**Stopping the zLux server**

The zLUX server is started as a Unix process.  To stop the zLUX server, use standard process signals such as SIGHUP, SIGTERM, and SIGKILL.  Alternatively, you can press CTRL+C if zLux is running in the foreground.

If you are running zLux in the background to end the server determine its task number by running `ps -elf | grep node` and running `kill -9 <taskname>` where the taskname is the process number of the node harmony process.

***Example***
```
 ps -elf | grep node
 TSTRADM   50397574   16843272  - 02:50:02 ttyp0002  0:00 node --harmony zluxServer.js --config=../deploy/instance/ZLUX/serverConfig/zlux
 TSTRADM   16843272      65777  - 02:50:02 ttyp0002  0:00 /bin/sh -- ./nodeServer.sh
 TSTRADM   50397763   16843272  - 02:50:02 ttyp0002  0:00 tee ../log/nodeServer-2018-05-18-02-50.log
 kill -9 50397574
```

