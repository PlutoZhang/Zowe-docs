# Setting the environment variables for plug-in development

The UNIX environment variables must be set appropriately before you can use the zLUX build procedures to develop your own plug-ins.

To set up the environment, the node must be accessible on the PATH. To determine if the node is on the PATH, issue the following command on the command line:

 ```
   node --version
``` 

If data is returned, the node is already on the PATH and no action is required.  

If nothing is returned from the command, you can set the PATH using the *NODE_HOME* variable. The *NODE_HOME* variable must be set to the directory of the node install. You can use the export command to set the directory. For example: 
```
export `NODE_HOME`=node_installation_directory
```
Using this directory, the node will be included on the PATH in `nodeServer.sh`. (`nodeServer.sh` is located in `zlux-example-server/bin`). 

 


