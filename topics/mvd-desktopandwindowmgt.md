# Virtual desktop and window management

The Virtual Desktop is a web component of Zoe, which is an implementation of MVDWindowManagement, the interface that is used to create a window manager.

The code for this software can be found in the [zlux-app-manager repository](https://github.com/gizafoundation/zlux-app-manager/tree/master/virtual-desktop/src/app/window-manager/mvd-window-manager) repository.

The interface for building an alternative window manager is present in [zlux-platform](https://github.com/gizafoundation/zlux-platform/blob/master/interface/src/mvd-window-management.d.ts).


Window Management acts upon Windows, which are visualizations of an instance of an application plug-in. Application plug-in are plug-ins of the type "application", and therefore the Virtual Desktop operates around a collection of plug-ins.

**NOTE:** 

* Other objects and frameworks that can be utilized by application plug-ins, but not related to Window Management, such as application-to-application communication, Logging, URI lookup, and Auth are not covered here.


# Loading and presenting application plug-ins
Upon loading the MVD, a GET call is made to ```/plugins?type=application```
This returns a JSON list of all application plug-ins that are present on the server, which can be accessed by the user. Application plug-ins can be composed of dataservices, web content, or both. Application plug-ins that have web content will be presented in the MVD UI.

The MVD presents a taskbar at the bottom of the page, where it presents each application plug-in as an icon with a description. The icon that is used, and description presented are based off of the application plug-in's PluginDefinition's webContent attributes.

# Plug-in management
Application plug-ins can gain insight into the environment they have been spawned in through the Plugin Manager. Use the Plugin Manager to check whether a plug-in is present before acting upon the existence of that plug-in. When the MVD is running, the Plugin Manager can be accessed through ```RocketMVD.PluginManager```

The following are functions you can use on the Plugin Manager:

* getPlugin(pluginID: string)
  * Accepts a string of a unique plug-in ID, and returns the Plugin Definition Object (DesktopPluginDefinition) that is associated with it, if found.


# Application management
Application plug-ins within a Window Manager are created and acted upon in part by an Application Manager. The Application Manager can facilitate communication between application plug-ins, but formal application-to-application communication should be performed by calls to the Dispatcher. The Application Manager is not normally accessible directly by application plug-ins, instead used by the Window Manager.

The following are functions of an Application Manager:
* spawnApplication(plugin: DesktopPluginDefinition, launchMetadata: any): Promise<MVDHosting.InstanceId>;
  * Opens an App instance into the Window Manager, with or without context on what actions it should perform after creation.
    
* killApplication(plugin:ZLUX.Plugin, appId:MVDHosting.InstanceId): void;
  * Removes an App instance from the Window Manager.
  
* showApplicationWindow(plugin: DesktopPluginDefinitionImpl): void;
  * Makes an open App instance visible within the Window Manager.
  
* isApplicationRunning(plugin: DesktopPluginDefinitionImpl): boolean;
  * Determines if any instances of the App are open in the Window Manager.    

# Windows and Viewports
When an application plug-in's icon is clicked on the taskbar, an instance of the application plug-in is started and presented within a Viewport, which is encapsulated in a Window within the Desktop.
Every instance of an application plug-in's web content within Zoe is given context and can listen on events about the Viewport and Window it exists within, regardless of if the Window Manager implementation utilizes these constructs visually. It is possible to create a Window Manager that only displays one application plug-in at a time, or to have a drawer-and-panel UI rather than a true windowed UI.

When the Window is created, the application plug-in's web content is encapsulated dependent upon its framework type. The following are valid framework types:

* "angular2": The web content is written in Angular, and packaged with Webpack. Application plug-in framework objects are given through @injectables and imports.
* "iframe": The web content can be written using any framework, but is included through an iframe tag. Application plug-ins within an iframe can access framework objects through parent.RocketMVD and callbacks.

In the case of the MVD, this framework-specific wrapping is handled by the [Plugin Manager](zlux-app-manager/virtual-desktop/src/app/plugin-manager).

# Viewport Manager
Viewports encapulate an instance of an application plug-in's web content, but otherwise do not add to the UI (they do not present chrome as a Window does).
Each instance of an application plug-in is associated with a viewport, and operations to act upon a particular application plug-in instance should be done by specifying a viewport for an application plug-in, to differentiate which instance is the target of an action. Actions performed against viewports should be done through the Viewport Manager.

The following are functions of the Viewport Manager:
* createViewport(providers: ResolvedReflectiveProvider[]): MVDHosting.ViewportId;
  * Creates a viewport for embedding an App's webcontent into.

* registerViewport(viewportId: MVDHosting.ViewportId, instanceId: MVDHosting.InstanceId): void;
  * Registers a previously created viewport to an App instance.

* destroyViewport(viewportId: MVDHosting.ViewportId): void;
  * Removes a viewport from the Window Manager.

* getApplicationInstanceId(viewportId: MVDHosting.ViewportId): MVDHosting.InstanceId | null;
  * Returns the ID of an App's instance from within a viewport within the Window Manager.
  

# Injection Manager
When Angular application plug-ins are made, they can utilize injectables to be informed of when an action happens. iframe application plug-ins indirectly benefit from some of these hooks due to the wrapper acting upon them, but Angular application plug-ins have direct access to these.

This section describes injectables that application plug-ins can utilize.

## Plug-in Definition
```@Inject(Angular2InjectionTokens.PLUGIN_DEFINITION) private pluginDefinition: ZLUX.ContainerPluginDefinition```

Provides the Plug-in Definition associated with this application plug-in. It can be used to gain some context about the application plug-in but also can be used by the application plug-in with other application plug-in framework objects to perform a contextual action.

## Logger
```@Inject(Angular2InjectionTokens.LOGGER) private logger: ZLUX.ComponentLogger```

Provides a logger that is named after the application plug-in's Plugin Definition ID. 

## Launch Metadata
```@Inject(Angular2InjectionTokens.LAUNCH_METADATA) private launchMetadata: any```

If present, this variable requests the application plug-in instance to initialize with some context, rather than the default view.

## Viewport Events
```@Inject(Angular2InjectionTokens.VIEWPORT_EVENTS) private viewportEvents: Angular2PluginViewportEvents```

Presents hooks that can be subscribed to for event listening. Events include:

* resized: Subject<{width: number, height: number}>
  * Fires when the viewport's size has changed.

## Window Events
```@Inject(Angular2InjectionTokens.WINDOW_ACTIONS) private windowActions: Angular2PluginWindowActions```

Presents hooks that can be subscribed to for event listening. Events include:
* maximized: Subject<void>
  * Fires when the Window has been maximized.

* minimized: Subject<void>
  * Fires when the Window has been minimized.

* restored: Subject<void>
  * Fires when the Window has been restored from a minimized state.

* moved: Subject<{top: number, left: number}>
  * Fires when the Window has been been moved.

* resized: Subject<{width: number, height: number}>
  * Fires when the Window has been resized.

* titleChanged: Subject<string>
  * Fires when the Window's title has changed.
  
## Window Actions
```@Inject(Angular2InjectionTokens.WINDOW_ACTIONS) private windowActions: Angular2PluginWindowActions```

An application plug-in can request actions to be performed on the Window through the following:

* close(): void
  * Closes the Window of the application plug-in instance.
  
* maximize(): void
  * Maximizes the Window of the application plug-in instance.
  
* minimize(): void
  * Minimizes the Window of the application plug-in instance.

* restore(): void
  * Restores the Window of the application plug-in instance from a minimized state.

* setTitle(title: string):void
  * Sets the title of the Window.

* setPosition(pos: {top: number, left: number, width: number, height: number}): void
  * Sets the position of the Window on the page, as well as the size of the window.

* spawnContextMenu(xPos: number, yPos: number, items: ContextMenuItem[]): void
  * Opens a context menu on the application plug-in instance, which uses the <Link: Context Menu framework>

* registerCloseHandler(handler: () => Promise<void>): void
  * Registers a handler which will be called when the Window and application plug-in instance are closed.
  