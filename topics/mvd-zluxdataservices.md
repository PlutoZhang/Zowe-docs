# zLUX Dataservices

Dataservices are a dynamic component of the backend of a zLUX App. Dataservices are optional, because the proxy server might only serve static content for a particular application. However, when included in an application, a dataservice defines a URL space for which the server will execute the extensible code from the application. Dataservices are primarily intended to be used to create REST APIs and Websocket channels.

## Defining a Dataservice
Observe a simple application: [sample-app](https://github.com/gizafoundation/sample-app). 
Within this repository, you will find a file in the top directory, `pluginDefinition.json`. Each zLUX application requires this file, because it defines how the server will register and use the backend of an application (called a plug-in in the terminology of the proxy server).

Within the JSON, there is a top level attribute, **dataServices**:
```
  "dataServices": [
    {
      "type": "router",
      "name": "hello",
      "serviceLookupMethod": "external",
      "fileName": "helloWorld.js",
      "routerFactory": "helloWorldRouter",
      "dependenciesIncluded": true
    }
  ]
```
### Dataservices defined in pluginDefinition

The following attributes are valid for each dataservice in the dataServices array:
* **type**: Valid values are "router" or "service".

  - **router**: Router dataservices are dataservices that will run under the proxy server, and use ExpressJS Routers for attaching actions to URLs and methods.
  - **service**: Service dataservices are dataservices that run under ZSS, and utilize the API of ZSS dataservices for attaching actions to URLs and methods.
- **name**: The name of the service that must be unique for each `pluginDefinition.json` file. This name is used to refer to the dataservice during logging, but also is used in construction of the URL space that the dataservice will occupy.

- **serviceLookupMethod**: Specify "external" unless otherwise instructed.

- **fileName**: The name of the file that is the entry point for construction of the dataservice, relative to the application's `/lib` folder. In the case of `sample-app`, you will see that upon transpilation of the typescript code, javascript files are placed into `/lib`.

- **routerFactory (Optional)**: When using a dataservice of type Router, the dataservice will be included in the proxy server through a require() statement. If the dataservice's exports are set up such that the Router is provided through a factory of a particular name, then you must state the name of the exported factory using this attribute.

- **dependenciesIncluded**: Must be **true** for anything in the `pluginDefinition.json` file. (This setting is only false when adding dataservices to the server dynamically.)

## Dataservice API
The API for a dataservice can categorized as: Router-based or ZSS-based, and Websocket or not.

**Note: Each Router dataservice can safely import express, express-ws and bluebird without requiring the modules to be present, because these modules exist in the proxy server's directory and the `NODE_MODULES` environment variable can include this directory.**

### Router-based Dataservices

#### HTTP/REST Router Dataservices

Router-based dataservices must return a (bluebird) Promise that resolves to an ExpressJS router upon success.
Check the ExpressJS guide on use of Router middleware to see the full capabilities this provides: [Using Router Middleware](http://expressjs.com/en/guide/using-middleware.html#middleware.router).

Because of the nature of Router middleware, the dataservice need only specify URLs that stem from a root '/' path, as the paths specified in the router will later be prepended with the unique URL space of the dataservice.

The Promise for the Router can be within a Factory export function, as mentioned in the pluginDefinition spec for **routerFactory** above, or by the module constructor.

Example: [Sample App backend](https://github.com/gizafoundation/sample-app/blob/master/nodeServer/ts/helloWorld.ts)

#### Websocket Router Dataservices

ExpressJS routers are fairly flexible, so the contract to create the Router for Websockets is not significantly different.

Here, [express-ws](https://www.npmjs.com/package/express-ws) is used, which adds websockets through [ws](https://www.npmjs.com/package/ws) to ExpressJS. The two changes between a websocket-based Router and a normal Router is that the method is 'ws', as in `router.ws(<url>,<callback>)`, and that the callback provides the websocket for which you must set up event listeners on.

Check the ws and express-ws pages linked above for more information about how they work, as the API for websocket router dataservices is primarily provided in these packages.

Example: [Terminal proxy](https://github.com/gizafoundation/zlux-proxy-server/blob/master/plugins/terminal-proxy/lib/terminalProxy.js#L710)

#### Router Dataservice Context

Every Router-based dataservice is provided with a Context object on creation that provides definitions of its surroundings and functions that are helpful. The following items are present in the Context:

- **serviceDefinition**: The dataservice definition, originally from the pluginDefinition.json file within a plug-in.
- **serviceConfiguration**: An object that contains the contents of configuration files, if present. 
- **logger**: An instance of a zLUX Logger, which has its component name as the unique name of the dataservice within a plug-in.
- **makeSublogger**: A function to create a zLUX Logger with a new name, which is appended to the unique name of the dataservice.
- **addBodyParseMiddleware**: A function that provides common body parsers for HTTP bodies, such as JSON and plaintext.
- **plugin**: An object that contains more context from the plugin scope. This includes the following:
  - **pluginDef**: The contents of the `pluginDefinition.json` file that this dataservice is a part of.
  - **server**: An object that contains information about the server's configuration. This includes the following:
    - **app**: Information about the product, which includes the productCode, such as ZLUX.
    - **user**: Configuration information of the server, such as the port on which it is listening.


