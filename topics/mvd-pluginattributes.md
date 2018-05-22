# Attributes

There are two categories of attributes: General and Application.

## General attributes

**identifier** - Every application plug-in must have a unique string ID that associates it with a URL space on the server.

**apiVersion** - The version number for the pluginDefinition scheme and application plug-in or Dataservice requirements. The default is 1.0.0.

**pluginVersion** - The version number of the individual plug-in.

**pluginType** -  A string that specifies the type of plug-in. The type of plug-in determines the other attributes that are valid in the definition.

-  **application** - Defines the plug-in as an application plug-in. Application plug-ins are composed of a collection of web content for presentation in the zLUX web component (such as the virtual desktop), or a collection of dataservices (REST and websocket), or both.

-  **library** -  Defines the plug-in as a library that serves static content at a known URL space.

-  **node authentication** - Authentication and  Authorization handlers for the zLUX Application Server.

## Application attributes

When a plug-in is of **pluginType** application, the following attributes are valid:

-  **webContent** - An object that defines a few attributes about the content that is shown in a web UI.

-  **dataServices** - An array of objects that describe REST or websocket dataservices.

-  **configurationData** - An object that describes the resource structure that the application plug-in uses for storing user, group, and server data.

## Application web content attributes

An application that has the **webContent** attribute defined provides content that is displayed in a zLUX web UI. 

The following attributes determine some of this behavior:

-  **framework** - States what type of web framework is used, which determines the other attributes that are valid in webContent.

  -  **angular2** - Defines the application as having an Angular (2+) web framework component. This is the standard for a "native" framework zLUX application.

  -  **iframe** - Defines the application as being external to the native zLUX web application environment, but instead embedded in an iframe wrapper.

-  **launchDefinition** - An object that details some attributes for presenting the application in a web UI.

    -  **pluginShortNameDefault** - A string that gives a name to the application when i18n is not present. When i18n is present, i18n is applied by using the pluginShortNameKey.

    -  **descriptionDefault** - A longer string that specifies a description of the application within a UI. The description is seen when i18n is not present. When i18n is present, i18n is applied by using the descriptionKey.

    -  **imageSrc** - The relative path (from `/web`) to a small image file that represents the application icon.

-  **defaultWindowStyle** - An object that details the placement of a default window for the application in a web UI.

    -  **width** - The default width of the application plug-in window, in pixels.

    -  **height** - The default height of the application plug-in window, in pixels.

##   IFrame application web content

In addition to the general web content attributes, when stating that the framework of an application is "iframe", you must state the page that is being embedded in the iframe. To do so, incude the attribute **startingPage** within **webContent**. **startingPage** is relative to the application's `/web` directory.

It is recommended that `startingPage` be a relative path rather than an absolute path as the `pluginDefinition.json` file is intended to be read-only, and therefore would not work well when the hostname of a page has changed.

Within an IFrame, the application still has access to the globals that are used by zLUX for application-to-application communication: simply access **window.parent.RocketMVD**.

