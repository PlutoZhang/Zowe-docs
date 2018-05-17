# zLUX logging

zLUX generates log files in the following default locations:

- Zoe Node Server: `zlux-example-server/log/nodeServer-yyyy-mm-dd-hh-mm.log`
- ZSS: `zlux-example-server /log/zssServer-yyyy-mm-dd-hh-mm.log`
 
Note that the Zoe Node Server logs and ZSS logs are timestamped in the format yyyy-mm-dd-hh-mm and older logs are deleted when a new log is created at server startup.

## Controlling the zLUX logging location

The server writes log information to a file and to the screen. (On Windows, logs are written to a file only.)

### ZLUX_NODE_LOG_DIR and ZSS_LOG_DIR environment variables

To control where the information is logged, use the environment variable *ZLUX_NODE_LOG_DIR*, for the Zoe Node Server, and *ZSS_LOG_DIR*, for ZSS. While these variables are intended to specify a directory, if you specify a location that is a file name, zLUX will write the logs to the specified file instead (for example: `/dev/null` to disable logging). 

When you specify the environment variables *ZLUX_NODE_LOG_DIR* and *ZSS_LOG_DIR* and they are directories rather than files, zLUX will perform timestamping and cleanup.

### ZLUX_NODE_LOG_FILE and ZSS_LOG_FILE environment variables

If you set the log file name for the node server by setting the *ZLUX_NODE_LOG_FILE* environment variable, or if you set the log file for ZSS by setting the *ZSS_LOG_FILE* environment variable, there will only be one log file, and it will be overwritten.

**NOTE**: When you set the *ZLUX_NODE_LOG_FILE* or *ZSS_LOG_FILE* environment variables, zLUX will not override the log names, set a timestamp, or delete the logs.

If zLUX cannot create the folder or file, the server will run (but it might not perform logging properly).

## Retaining logs
By default, zLUX retains the last five logs. If you want to specify a different number of logs to retain, set *ZLUX_NODE_LOGS_TO_KEEP* (Zoe Node Server logs) or *ZSS_LOGS_TO_KEEP* (ZSS logs) to the number of logs that you want to keep. The default is 5.
