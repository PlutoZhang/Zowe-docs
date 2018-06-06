
# Plug-in Definition

Because the Configuration Dataservices stores data on a per-plug-in basis, each zLUX plug-in must define their resource structure to make use of the Configuration Dataservice. The resource structure definition is included in the plug-in's `pluginDefinition.json` file.

For each resource and subresource, you can define an aggregationPolicy to control how the data of a broader Scope alters the resource data that is returned to a user when requesting a resource from a narrower Scope.

Example:
```
  "configurationData": { //is a direct attribute of the pluginDefinition JSON
    "resources": { //always required
      "preferences": {
        "locationType": "relative", //this is the only option for now, but later absolute paths may be accepted
        "aggregationPolicy": "override" //override and none for now, but more in the future
      },
      "sessions": { //the name at this level represents the name used within a URL, such as /plugins/com.rs.configjs/services/data/org.openmainframe.zoe.codeeditor/user/sessions
        "aggregationPolicy": "none",
        "subResources": {
          "sessionName": {
            "variable": true, //if variable=true is present, the resource must be the only one in that group but the name of the resource is substituted for the name given in the REST request, so it represents more than one
            "aggregationPolicy": "none"
          }
        }
      }
    }
  }
```
