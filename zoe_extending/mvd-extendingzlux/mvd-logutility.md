# Logging utility

## Logging utility

[zlux-shared](https://github.com/gizafoundation/zlux-shared/tree/master/src/logging) provides a logging utility for use by both dataservices and web content for a Zoe application plug-in.

## Logging objects

This logging utility is based on three objects:

* **Component Loggers** - Objects that log messages for an individual component of the environment, such as a REST API for an application plug-in or to log user access.
* **Destinations** - Objects that are called when a component logger requests a message to be logged. Destinations determine how something is logged, for example, to a file or to a console, and what formatting is applied.
* **Logger** - Central logging object, which can spawn component loggers and attach destinations.

## Logger IDs

Because Zoe application plug-in have unique identifiers, both dataservices and an application plug-in's web content are provided with a component logger that knows this unique ID such that messages logged can be prefixed with that ID. With the association of logging to IDs, verbosity of logs can be controlled by setting log verbosity by ID.

## Accessing logger objects

### Logger

The core logger object is attached as a global for low-level access.

#### zLUX Application Server

NodeJS uses `global` as its global object, so the logger is attached to: `global.COM_RS_COMMON_LOGGER`

#### Web

Browsers use `window` as the global object, so the logger is attached to: `window.COM_RS_COMMON_LOGGER`

### Component logger

Component loggers are created from the core logger object, but when working with an application plug-in, allow the application plug-in framework to create these loggers for you. An application plug-in's component logger is presented to dataservices or web content as follows.

#### App Server

See **Router Dataservice Context** in the topic [zLUX dataservices](mvd-zluxdataservices.md).

#### Web

\(Angular App Instance Injectible\). See **Logger** in [Desktop and window management](mvd-desktopandwindowmgt.md).

## Logger API

The following constants and functions are available on the central logging object.

| Attribute | Type | Description | Arguments |
| --- | --- | --- | --- |
| makeComponentLogger | function | Creates a component logger - Automatically done by the App framework for dataservices and web content | componentIDString |
| setLogLevelForComponentName | function | Sets the verbosity of an existing component logger | componentIDString, logLevel |

## Component Logger API

The following constants and functions are available to each component logger.

| Attribute | Type | Description | Arguments |
| --- | --- | --- | --- |
| SEVERE | const | Is a const for logLevel |  |
| WARNING | const | Is a const for logLevel |  |
| INFO | const | Is a const for logLevel |  |
| FINE | const | Is a const for logLevel |  |
| FINER | const | Is a const for logLevel |  |
| FINEST | const | Is a const for logLevel |  |
| log | function | Used to write a log, specifying the log level | logLevel, messageString |
| severe | function | Used to write a SEVERE log. | messageString |
| warn | function | Used to write a WARNING log. | messageString |
| info | function | Used to write an INFO log. | messageString |
| debug | function | Used to write a FINE log. | messageString |
| makeSublogger | function | Creates a new component logger with an ID appended by the string given | componentNameSuffix |

## Log Levels

An enum, `LogLevel`, exists for specifying the verbosity level of a logger. The mapping is:

| Level | Number |
| --- | --- |
| SEVERE | 0 |
| WARNING | 1 |
| INFO | 2 |
| FINE | 3 |
| FINER | 4 |
| FINEST | 5 |

**NOTE:** The default log level for any logger is **INFO**.

## Logging verbosity

Using the component logger API, loggers can dictate at which level of verbosity a log message should be visible. The user can configure the server or client to show more or less verbose messages by using the [core logger's API objects](mvd-logutility.md#logger-api).

Example: You want to set the verbosity of the org.zoe.foo application plug-in's dataservice, bar to show debugging information. `logger.setLogLevelForComponentName('org.zoe.foo.bar',LogLevel.DEBUG)`

### Configuring logging verbosity

The application plug-in framework provides ways to specify what component loggers you would like to set default verbosity for, such that you can easily turn logging on or off.

#### Server startup logging configuration

The server configuration file, allows for specification of default log levels, as a top-level attribute 'logLevel', which takes key-value pairs where the key is a regex pattern for component IDs, and the value is an integer for the log levels.

For example:

```text
"logLevel": {
    "com.rs.configjs.data.access": 2,
    //the string given is a regex pattern string, so .* at the end here will cover that service and its subloggers.
    "com.rs.myplugin.myservice.*": 4
    //
    // '_' char reserved, and '_' at beginning reserved for server. Just as we reserve
    // '_internal' for plugin config data for config service.
    // _unp = universal node proxy core logging
    //"_unp.dsauth": 2
  },
```

For more information about the server configuration file, see [Configuring the zLUX Proxy Server and ZSS](https://github.com/PlutoZhang/Zoe-docs/tree/765a97073f853ac8f6cca084d9c9e90c1e4c8de9/topics/mvd-configzluxproxyandzss.md).

