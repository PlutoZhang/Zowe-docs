# Setting environment variables for plug-in development

To set up the environment, the node must be accessible on the PATH. To determine if the node is already on the PATH, issue the following command from the command line:

```text
node --version
```

If the version is returned, the node is already on the PATH.

If nothing is returned from the command, you can set the PATH using the _NODE\_HOME_ variable. The _NODE\_HOME_ variable must be set to the directory of the node install. You can use the export command to set the directory. For example:

```text
export NODE_HOME=node_installation_directory
```

Using this directory, the node will be included on the PATH in `nodeServer.sh`. \(`nodeServer.sh` is located in `zlux-example-server/bin`\).

