# zLUX logging

zLUX generates log files in the following default locations:

* Zoe Node Server: `zlux-example-server/log/nodeServer-yyyy-mm-dd-hh-mm.log`
* ZSS: `zlux-example-server/log/zssServer-yyyy-mm-dd-hh-mm.log`

Note that the Zoe Node Server logs and ZSS logs are timestamped in the format yyyy-mm-dd-hh-mm and older logs are deleted when a new log is created at server startup.

## Controlling the zLUX logging location

The zLUX server writes log information to a file and to the screen. \(On Windows, logs are written to a file only.\)

### ZLUX\_NODE\_LOG\_DIR and ZSS\_LOG\_DIR environment variables

To control where the information is logged, use the environment variable _ZLUX\_NODE\_LOG\_DIR_, for the Zoe Node Server, and _ZSS\_LOG\_DIR_, for ZSS. While these variables are intended to specify a directory, if you specify a location that is a file name, zLUX will write the logs to the specified file instead \(for example: `/dev/null` to disable logging\).

When you specify the environment variables _ZLUX\_NODE\_LOG\_DIR_ and _ZSS\_LOG\_DIR_ and they are directories rather than files, zLUX will perform timestamping and cleanup.

### ZLUX\_NODE\_LOG\_FILE and ZSS\_LOG\_FILE environment variables

If you set the log file name for the node server by setting the _ZLUX\_NODE\_LOG\_FILE_ environment variable, or if you set the log file for ZSS by setting the _ZSS\_LOG\_FILE_ environment variable, there will only be one log file, and it will be overwritten.

**NOTE**: When you set the _ZLUX\_NODE\_LOG\_FILE_ or _ZSS\_LOG\_FILE_ environment variables, zLUX will not override the log names, set a timestamp, or delete the logs.

If zLUX cannot create the folder or file, the server will run \(but it might not perform logging properly\).

## Retaining logs

By default, zLUX retains the last five logs. If you want to specify a different number of logs to retain, set _ZLUX\_NODE\_LOGS\_TO\_KEEP_ \(Zoe Node Server logs\) or _ZSS\_LOGS\_TO\_KEEP_ \(ZSS logs\) to the number of logs that you want to keep. The default is 5.

