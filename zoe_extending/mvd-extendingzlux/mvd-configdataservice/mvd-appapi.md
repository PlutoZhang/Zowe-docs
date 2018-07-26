# Application API

Retrieves and stores configuration information from specific scopes.

**NOTE: This API should only be used for configuration administration user interfaces.**

`ZLUX.UriBroker.pluginConfigForScopeUri(pluginDefinition: ZLUX.Plugin, scope: string, resourcePath:string, resourceName:string): string;`

A shortcut for the preceding method, and the preferred method when you are retrieving configuration information is simply to "consume" it. It "asks" for configurations using the "user" scope, and lets the configuration service decide which configuration information to retrieve and how to aggregate it. \(See below on how the configuration service evaluates what to return for this type of request\).

`ZLUX.UriBroker.pluginConfigUri(pluginDefinition: ZLUX.Plugin, resourcePath:string, resourceName:string): string;`

