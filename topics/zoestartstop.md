# Starting and stopping the Zoe runtime on z/OS

Zoe has two runtime components on z/OS, the explorer server and the zLUX server.  When you run the ZOESVR PROC, it starts both these components.  The zLUX server startup script also starts the zSS server, so starting the ZOESVR PROC starts all three servers, and stopping it stops all three.  

**Starting the ZOESVR PROC**

To start the ZOESVR PROC, run the `zoe-start.sh` script at the Unix Systems Services command prompt:

```
cd $ZOE_ROOT_DIR/scripts
./zoe-start.sh
```
where _$ZOE_ROOT_DIR_ is the directory where you installed the Zoe runtime.  This script starts the ZOESVR PROC for you so you don't have to log on to TSO and use SDSF.

If you prefer to use SDSF to start Zoe, start ZOESVR by issuing the following operator command in SDSF:

```
/S ZOESVR
```

By default, Zoe uses the runtime version that you most recently installed.  To start a different runtime, specify its server path on the START command:

```
/S ZOESVR,SRVRPATH='$ZOE_ROOT_DIR/explorer-server'
```

To test whether the explorer server is active, open the URL `https://<hostname>:7443/ui`.

The port number 7443 is the default port and can be overridden through the `zoe-install.yaml` file before the `zoe-install.sh` script is run. See [Installing Zoe runtime on z/OS](zoeinstall.md).

**Stopping the ZOESVR PROC**

To stop the ZOESVR PROC, run the `zoe-stop.sh` script at the Unix Systems Services command prompt:

```
cd $ZOE_ROOT_DIR/scripts
./zoe-stop.sh
```

If you prefer to use SDSF to stop Zoe, stop ZOESVR by issuing the following operator command in SDSF:

```
/C ZOESVR  
```
Either of the methods will stop the explorer server, the zLUX server, and the zSS server.

When you stop the ZOESVR, you might get the following error message:

```IEE842I ZOESVR DUPLICATE NAME FOUND- REENTER COMMAND WITH 'A='```

This is because there is more than one started task named ZOESVR. To resolve the issue, stop the required ZOESVR instance by using one of the following methods:

- Issue the following commands:

  ```/C ZOESVR,A=asid```

   You can obtain the _asid_ from the value of `A=asid` when you issue the following commands:

   ```/D A,ZOESVR```

- Select the instance in SDSF and type `C` for CANCEL in the NP column next to the job.
