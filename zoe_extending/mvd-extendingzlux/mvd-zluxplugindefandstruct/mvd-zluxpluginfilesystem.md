# Plug-in filesystem structure

A zLUX application plug-in can be loaded from a filesystem that is accessible to the zLUX Application Server, or dynamically at runtime. When accessed from a filesystem, there are important considerations for both the developer and the end-user as to where files must be placed for proper build, packaging, and operation.

## Root files and directories

The root of an application plug-in directory contains the following files and directories.

### pluginDefinition.json

This file describes an application plug-in to the zLUX Application Server. \(A plug-in is the unit of extensibility for the zLUX Application server. An application plug-in is a plugin of the type "Application", the most common and visible type of plug-in\). A definition file informs the server whether the application plug-in has server-side Dataservices, client-side web content, or both.

## Dev and Source content

Aside from demonstration or open source application plug-ins, the following directories should not be seen on a deployed server \(the directories are used to build content and are not read by the server\).

### nodeServer

When an application plug-in has Dataservices of the type "router", they are interpreted by the zLUX Application Server by attaching them as ExpressJS routers. Ir is recommended that you write application plug-ins using Typescript, because it leads to more well-structured code than Javascript. Use of Typescript results in build steps because the pre-transpilation Typescript content is not to be consumed by NodeJS. Therefore, within nodeServer, you keep your server-side source code. At runtime, the server loads router dataservices from the `lib` directory.

### webClient

When an application plug-in has the webContent attribute in its Definition, the server will serve static content for a client. To optimize loading of the application plug-in to the user, use Typescript to write the application plug-in and package it using Webpack. Use of Typescript and Webpack result in build steps as the pre-transpilation Typescript and the pre-webpack content are not to be consumed by the browser. Therefore, the source code should be separated from the served content by placing source code within webClient.

## Runtime content

At runtime, a different set of directories are used by the server and client rather than those described for use in the dev environment.

### lib

The `lib` directory is where router-type Dataservices are loaded by use in the zLUX Application Server. If the JS files that are loaded from the `lib` directory require NodeJS modules, which are not provided by the server base \(modules zlux-proxy-server requires are added to `NODE_PATH` at runtime\), then these modules must be included in lib/node\_modules for local directory lookup or be found on the `NODE_PATH` environment variable. `nodeServer/node_modules` is not automatically accessed at runtime as it is a dev and build directory.

### web

The `web` directory is where the server will serve static content for an application plug-in that includes the **webContent** attribute in its Definition. Typically this directory contains the output of a webpack build. Anything put in this folder can be accessed by a client, so only include content in this location that is intended to be consumed by clients.

