# Aggregation policies

Aggregation Policies determine how the Configuration Dataservice aggregates JSON objects from different Scopes together when a user requests a resource. If the user requests a resource from the User scope, the data from the User scope may replace, or be merged with the data from a broader scope such as Instance, to make a combined resource object that is returned to the user.

Aggregation Policies are defined by a plug-in developer in the plug-in's definition for the Configuration Service, as the attribute "aggregationPolicy" within a resource.

The following policies are currently implemented:

* **NONE** -  If the Configuration Dataservice is called for Scope User, only user-saved settings are sent, unless there are no user-saved settings for the query, in which case the Dataservice attempts to send data found at a more broad scope.
* **OVERRIDE** - The Configuration Dataservice obtains data for the resource that is requested at the broadest level found, and joins together the resource's properties from more narrow scopes, overriding broader attributes with narrower ones, when found.

