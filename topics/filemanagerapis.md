# File Manager APIs

Review the following table for detailed information about File Manager APIs. To use the File Manager APIs, File Manager must be installed.

|REST API|Description|Scenario|Prerequisites|
|--------|-----------|--------|-------------|
|`GET /FileManager/api/collections`|Get a list of members from the File Manager Enhanced Search dataset.|Use this API to get a list of the members in the File Manager Enhanced Search index data set. These members represent collections of data sources against which a File Manager enhanced search can be executed.|z/OSMF restfiles|
|`GET /FileManager/api/collections/{name}`|Read content from a File Manager Enhanced Search dataset member.|If you know the name of an enhanced search index member, you can read the content and pass it to File Manager Enhanced Search API.|z/OSMF restfiles|
|`PUT /FileManager/api/collections/{name}`|Write content to a File Manager Enhanced Search dataset member.|Use this API to update the content of a File Manager Enhanced Search index data set member.|z/OSMF restfiles|
|`POST /FileManager/api/collections/{name}`|Create a File Manager Enhanced Search dataset member.|Use this API to create a File Manager Enhanced Search index data set member.|z/OSMF restfiles|
|`DELETE /FileManager/api/collections/{name}`|Delete a File Manager Enhanced Search dataset member.|Use this API to delete a File Manager Enhanced Search index data set member.|z/OSMF restfiles|
|`GET /FileManager/api/search`|Perform a File Manager Enhanced Search.|Use this API to execute a File Manager Enhanced Search and return the result as JSON content.|IBM® File Manager|

**Parent topic:** [Using Atlas REST APIs](../topics/usingatlasrestapis.md)

