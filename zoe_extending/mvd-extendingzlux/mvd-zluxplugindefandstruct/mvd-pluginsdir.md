# Location of plug-in files

The files that define a plug-in are located in the `pluginsDir` directory.

## pluginsDir directory

At start up, the server reads from the `pluginsDir` directory. The server loads the valid plug-ins that are found by the information that is provided in the JSON files.

Within the `pluginsDir` directory are a collection of JSON files. Each file has two attributes, which serve to locate a plug-in on disk:

**location**: This is a directory path that is relative to the server's executable \(such as `zlux-example-server/bin/nodeServer.sh`\) at which a `pluginDefinition.json` file is expected to be found.

**identifier**: The unique string \(commonly styled as a Java resource\) of a plug-in, which must match what is in the `pluginDefinition.json` file.

