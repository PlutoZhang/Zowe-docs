# Set environmental variables for Zoe Brightside
You can set environment variables on your operating system to modify Zoe Brightside behavior, such as the log level and the location of the *.brightside* directory, where the logs, profiles, and plug-ins are
stored. Refer to your PC operating system documentation for information
about how to set environmental variables.

## Set log levels

You can set the log level to adjust the level of detail that is written to log files:

**Important\!** Setting the log level to TRACE or ALL may result in "sensitive" data being logged. For example, command line arguments will be logged when TRACE is set.

| Environmental Variable | Description | Values | Default |
| ---------------------- | ----------- |------- | ------- |
| BRIGHTSIDE\_APP\_LOG\_LEVEL        | Zoe Brightside logging level            | Log4JS log levels (OFF, TRACE, DEBUG, INFO, WARN, ERROR, FATAL) | DEBUG   |
| BRIGHTSIDE\_IMPERATIVE\_LOG\_LEVEL | Imperative CLI Framework logging level | Log4JS log levels (OFF, TRACE, DEBUG, INFO, WARN, ERROR, FATAL) | DEBUG   |

## Set the .brightside directory
You can set the location on your PC where Zoe Brightside creates the *.brightside* directory, which contains log files, profiles, and plug-ins for the product:

<div class="table-wrap">

| Environmental Variable | Description | Values | Default |
| ---------------------- | ----------- | ------ | ------- |
| BRIGHTSIDE\_CLI\_HOME  | Zoe Brightside home directory location | Any valid path on your PC | Your PC default home directory |

