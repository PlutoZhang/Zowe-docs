# Resource Scope

Data is stored within the Configuration Dataservice according to the Scope chosen.The intent of Scope within the Dataservice is to facilitate company-wide administration and privilege management of zLUX data.

When a user requests a resource, the resource that is retrieved is override or an aggregation of the broader Scopes that encompass the Scope they are viewing the data from.

When a user stores an resource, the resource is stored within a Scope but only if the user has access privilege to update within that Scope.

Scope is one of the following:

* **Product**: Configuration defaults that come with the product. Cannot be modified.
* **Site**: Data that can be used between multiple instances of the zLUX server.
* **Instance**: Data within an individual zLUX server.
* **Group**: Data shared between multiple users in a group (**Pending**)
* **User**: Data for an individual user (**Pending**)


Where **Product** is the broadest scope and **User** is the narrowest scope.

When using scope **User**, the service will manage configuration for your particular username, using the authentication of the session. This way, the **User** scope is always mapped to your current username.


Consider a case where a user wants to access preferences for their text editor. One way they could do this is to use the REST API to retrieve the settings resource from the **Instance** scope.

The **Instance** scope might contain editor defaults that their administrator set. But, if there were no defaults in Instance, then the data in **Group** and finally **User** would be checked.

Therefore, the data the user receives would be no broader than what is stored in the **Instance** scope, but may have only been the settings they had saved within their own **User** scope if the broader scopes had no data for the resource.

Later, perhaps the user wants to save changes, and they try to save in the **Instance** scope. Most likely, this is rejected due to preferences by the administrator to disallow changes to the **Instance** scope by ordinary users.

