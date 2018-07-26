# URI Broker

## URI Broker

The URI Broker is an object in the application plug-in web framework, which facilitates calls to the zLUX Application Server by constructing URIs that utilize the context from the calling application plug-in.

## Accessing the URI Broker

The URI Broker is accessible independent of other frameworks involved such as Angular, and is also accessible through iframe. This is because it is attached to a global when within the MVD. For more information, see [Desktop and window management](mvd-desktopandwindowmgt.md). Access the URI Broker through one of two locations:

Natively:

`window.RocketMVD.uriBroker`

In an iframe:

`window.parent.RocketMVD.uriBroker`

## Functions

The URI Broker builds different categories of URIs depending upon what the application plug-in is designed to call. Each category is listed below.

### Accessing an application plug-in's dataservices

zLUX dataservices can be based on HTTP \(REST\) or Websocket. For more information, see [zLUX dataservices](mvd-zluxdataservices.md).

#### HTTP Dataservice URI

* `pluginRESTUri(plugin:ZLUX.Plugin, serviceName: string, relativePath:string): string`

Returns: A URI for making an HTTP service request.

#### Websocket Dataservice URI

* `pluginWSUri(plugin: ZLUX.Plugin, serviceName:string, relativePath:string): string`

Returns: A URI for making a Websocket connection to the service.

### Accessing application plug-in's configuration resources

Defaults and user storage may exist for an application plug-in such that they can be retrieved through the Configuration Dataservice. There are different scopes and actions to take with this service, and therefore there are a few URIs that can be built:

#### Standard configuration access

* `pluginConfigUri(pluginDefinition: ZLUX.Plugin, resourcePath:string, resourceName?:string): string`

Returns: A URI for accessing the requested resource under the user's storage.

#### Scoped configuration access

* `pluginConfigForScopeUri(pluginDefinition: ZLUX.Plugin, scope: string, resourcePath:string, resourceName?:string): string`

Returns: A URI for accessing a specific scope for a given resource.

### Accessing static content

Content under an application plug-in's `web` directory is static content accessible by a browser. This can be accessed through:

* `pluginResourceUri(pluginDefinition: ZLUX.Plugin, relativePath: string): string`

Returns: A URI for getting static content.

For more information about the `web` directory, see [zLUX application filesystem structure](https://github.com/PlutoZhang/Zoe-docs/tree/765a97073f853ac8f6cca084d9c9e90c1e4c8de9/topics/topics/mvd-zluxappfilesystem.md).

### Accessing the application plug-in's root

Static content and services are accessed off of the root URI of an application plug-in. If there are other points that you need to access on that application plug-in, you can get the root:

* `pluginRootUri(pluginDefinition: ZLUX.Plugin): string`

Returns: A URI to the root of the application plug-in.

### Server queries

A client can find different information about a server's configuration or the configuration as seen by the current user by accessing specific APIs.

#### Accessing a ist of plug-ins

* `pluginListUri(pluginType: ZLUX.PluginType): string`

Returns: A URI which when accessed will return the list of existing plug-ins on the server by the type specified, such as "Application" or "all".

