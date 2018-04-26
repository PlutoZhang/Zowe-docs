# zLUX logging

By default, zLUX generates logs in the following locations:

- Giza Node server: `zlux-example-server/log/nodeServer-{TIMESTAMP}.log`
- ZSS: `zlux-example-server /log/zssServer-{TIMESTAMP}.log`
 
Note that the Giza Node server logs and ZSS logs are timestamped and older logs are deleted when a new log is created at server startup.

## Controlling the logging location

The server writes logs to a file and to the screen. (On Windows, logs are written to a file only.)

### ZLUX_NODE_LOG_DIR and ZSS_LOG_DIR environment variables

You can control the logging location through the environment variables ZLUX_NODE_LOG_DIR (the Giza Node server) and ZSS_LOG_DIR (ZSS). While these variables are intended to specify a directory, if you specify a location that is a file name, zLUX will write the logs to the specified file instead (for example: `/dev/null` to disable logging). 

When you specify the environment variables ZLUX_NODE_LOG_DIR and ZSS_LOG_DIR and they are directories rather than files, zLUX will perform timestamping and cleanup.

### ZLUX_NODE_LOG_FILE and ZSS_LOG_FILE environment variables

If you set the log file name for the node server by setting the ZLUX_NODE_LOG_FILE environment variable, or if you set the log file for ZSS by setting the ZSS_LOG_FILE environment variable, there will only be one log file, and it will be overwritten.

**NOTE**: When you set the ZLUX_NODE_LOG_FILE or ZSS_LOG_FILE environment variables, zLUX will not override the log names, set a timestamp, or delete the logs.

If zLUX encounters a problem in creating the folder or file, the server will run (but it might not perform logging properly).

## Retaining logs
By default, zLUX retains the last five logs. If you want to specify a different number of logs to retain, set ZLUX_NODE_LOGS_TO_KEEP (Giza Node Server logs) or ZSS_LOGS_TO_KEEP (ZSS logs) to the number of logs that you want to keep. The default is 5.
