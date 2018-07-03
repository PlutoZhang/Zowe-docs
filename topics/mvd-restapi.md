
# REST API

When reaching the Configuration Service through a REST API, HTTP methods are used to perform the desired operation.

The HTTP URL scheme for the configuration dataservice is:

**`<Server>/plugins/com.rs.configjs/services/data/<plugin ID>/<Scope>/<resource>/<optional subresources>?<query>`**

Where the resources are one or more levels deep, using as many layers of subresources as needed.

You can think of a resource as a collection of elements, or a directory. To access a single element, you must use the query parameter "name="


## REST query parameters

* **Name** (string) - Get or put a single element rather than a collection.
* **Recursive** (boolean) - When performing a DELETE, specifies whether to delete subresources.


## REST HTTP methods

Below is an explanation of each type of REST call.
Each API call includes an example request and response against a hypothetical application: the "code editor".

### GET
**GET `/plugins/com.rs.configjs/services/data/<plugin>/<scope>/<resource>?name=<element>`**

  * This returns JSON with the attribute "content" being a JSON resource that is the entire configuration requested.
  * Example:

  ```/plugins/com.rs.configjs/services/data/org.openmainframe.zoe.codeeditor/user/sessions/default?name=tabs```

  * The parts of the URL are:
    * Plugin: org.openmainframe.zoe.codeeditor
    * Scope: user
    * Resource: sessions
    * Subresource: default
    * Element = tabs

  * Response body is a JSON config:
```
{
	"_objectType" : "com.rs.config.resource",
	"_metadataVersion" : "1.1",
	"resource" : "org.openmainframe.zoe.codeeditor/USER/sessions/default",
	"contents" : {
		"_metadataVersion" : "1.1",
		"_objectType" : "org.openmainframe.zoe.codeeditor.sessions.tabs",
		"tabs" : [{
				"title" : "TSSPG.REXX.EXEC(ARCTEST2)",
				"filePath" : "TSSPG.REXX.EXEC(ARCTEST2)",
				"isDataset" : true
			}, {
				"title" : ".profile",
				"filePath" : "/u/tsspg/.profile"
			}
		]
	}
}
```

**GET `/plugins/com.rs.configjs/services/data/<plugin>/<scope>/<resource>`**

  * This returns JSON with the attribute "content" being a JSON object that has each attribute being another JSON object which is a single configuration element.

**GET `/plugins/com.rs.configjs/services/data/<plugin>/<scope>/<resource>`** when subresources exist

  * This returns a listing of subresources that can, in turn, be queried.

### PUT

**PUT `/plugins/com.rs.configjs/services/data/<plugin>/<scope>/<resource>?name=<element>`**

  * Stores a single element (must be a JSON object {...}) within the requested scope, ignoring aggregation policies, provided the privilege of the user permits this.

  * Example: ```/plugins/com.rs.configjs/services/data/org.openmainframe.zoe.codeeditor/user/sessions/default?name=tabs```

  * Body:

```
{
  "_metadataVersion" : "1.1",
  "_objectType" : "org.openmainframe.zoe.codeeditor.sessions.tabs",
  "tabs" : [{
      "title" : ".profile",
      "filePath" : "/u/tsspg/.profile"
    }, {
      "title" : "TSSPG.REXX.EXEC(ARCTEST2)",
      "filePath" : "TSSPG.REXX.EXEC(ARCTEST2)",
      "isDataset" : true
    }, {
      "title" : ".emacs",
      "filePath" : "/u/tsspg/.emacs"
    }
  ]
}

```
  * Response:

```
{
  "_objectType" : "com.rs.config.resourceUpdate",
  "_metadataVersion" : "1.1",
  "resource" : "org.openmainframe.zoe.codeeditor/USER/sessions/default",
  "result" : "Replaced item."
}
```

### DELETE

**DELETE `/plugins/com.rs.configjs/services/data/<plugin>/<scope>/<resource>?recursive=true`**

  * Deletes all files in all leaf resources below the resource specified.

**DELETE `/plugins/com.rs.configjs/services/data/<plugin>/<scope>/<resource>?name=<element>`**

  * Deletes a single file in a leaf resource.

**DELETE `/plugins/com.rs.configjs/services/data/<plugin>/<scope>/<resource>`**

  * Deletes all files in a leaf resource.
  * Does not delete the folder on disk.


## Administrative access and group

By means not discussed here, but instead handled by the server's authentication and authorization code, a user might be privileged to access or modify items that they do not own.

In the simplest case, it might mean that the user is able to do a PUT, POST, or DELETE to a level above User, such as Instance.

The more interesting case is accessing another user's contents. In this case, the shape of the URL is different. Compare the following two commands:

**GET `/plugins/com.rs.configjs/services/data/<plugin>/user/<resource>`**

  *  Gets the content for the current user

**GET `/plugins/com.rs.configjs/services/data/<plugin>/users/<username>/<resource>`**

  *  Gets the content for a specific user if authorized

This is the same structure that is (or will be) used for the Group scope. When requesting content from the Group scope, the user is checked to see if they are authorized to make the request for the specific group. For example:

**GET `/plugins/com.rs.configjs/services/data/<plugin>/group/<groupname>/<resource>`**

  * Gets the content for the given group, if the user is authorized for it.
