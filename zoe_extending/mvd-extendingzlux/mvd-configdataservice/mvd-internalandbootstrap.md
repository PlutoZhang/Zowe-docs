# Internal and bootstrapping

Some Dataservices within plug-ins can take configuration that affects their behavior. This configuration is stored within the Configuration Dataservice structure, but is not accessible through the REST API.

Within the deploy directory of a zLUX installation, each plug-in may optionally have an `_internal` directory. An example of such a path is:

`deploy/instance/ZLUX/pluginStorage/<pluginName>/_internal`

Within each \_internal folder, the following folders may exist:

* `services/<servicename>`: Configuration resources for the specific service.
* plugin: Configuration resources visible to all services in the plug-in.

The JSON contents within these directories will be provided as Objects to dataservices through the dataservice context Object.

