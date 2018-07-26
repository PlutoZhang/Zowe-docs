# Table of contents

* [Introduction](README.md)
* [Edition notice](editionnotice.md)
* [About this guide](aboutthisbook.md)
* [Summary of changes](summaryofchanges.md)
* [Known issues](known-issues.md)
* [Project Zoe overview](zoe-introduction/README.md)
  * [zLUX](zoe-introduction/mvd-overview.md)
  * [Explorer server](zoe-introduction/atlas-overview.md)
  * [Zoe Brightside](zoe-introduction/cli-releasenotes.md)
* [Installing Project Zoe](installandconfig/README.md)
  * [Installation roadmap](installandconfig/installroadmap.md)
  * [System requirements](installandconfig/planinstall/README.md)
    * [z/OSMF configuration](installandconfig/planinstall/prezosmf.md)
    * [System requirements for zLUX](installandconfig/planinstall/premvd/README.md)
      * [Confirming that Node.js is installed](installandconfig/planinstall/premvd/mvd-instconfirmnodejsinstalled.md)
      * [Configuring ports for the zLUX terminal application plug-ins](installandconfig/planinstall/premvd/mvd-configterminalappports.md)
    * [System requirements for explorer server](installandconfig/planinstall/atlas-prereqs.md)
    * [System requirements for Zoe Brightside](installandconfig/planinstall/cli-precli.md)
  * [Obtaining installation files](installandconfig/zoegettingstarted.md)
  * [Installing zLUX and explorer server](installandconfig/zoeinstall-zos/README.md)
    * [Installing Zoe runtime on z/OS](installandconfig/zoeinstall-zos/zoeinstall.md)
    * [Starting and stopping the Zoe runtime on z/OS](installandconfig/zoeinstall-zos/zoestartstop.md)
    * [Verifying installation](installandconfig/zoeinstall-zos/verify/README.md)
      * [Verifying zLUX installation](installandconfig/zoeinstall-zos/verify/mvd-instopendesktopbrowser/README.md)
        * [Setting up the terminal application plug-ins](installandconfig/zoeinstall-zos/verify/mvd-instopendesktopbrowser/mvd-settingupterminalapps.md)
      * [Verifying explorer server installation](installandconfig/zoeinstall-zos/verify/atlas-verifyinstall.md)
    * [Troubleshooting installing the Zoe runtime](installandconfig/zoeinstall-zos/zoeinstalltroubleshoot/README.md)
      * [Troubleshooting installing zLUX](installandconfig/zoeinstall-zos/zoeinstalltroubleshoot/mvd-troubleshoot.md)
      * [Troubleshooting installing explorer server](installandconfig/zoeinstall-zos/zoeinstalltroubleshoot/atlas-troubleshoot.md)
  * [Installing Zoe Brightside](installandconfig/cli-installcli/README.md)
    * [Creating a Zoe Brightside profile](installandconfig/cli-installcli/cli-createaprofile.md)
    * [Verifying Zoe Brightside connection to z/OSMF](installandconfig/cli-installcli/cli-validateinstallation.md)
    * [Troubleshooting installing Zoe Brightside](installandconfig/cli-installcli/cli-troubleshootinginstallingcli.md)
  * [Uninstalling Project Zoe](installandconfig/uninstall/README.md)
    * [Uninstalling zLUX](installandconfig/uninstall/mvd-uninstallingzlux.md)
    * [Uninstalling explorer server](installandconfig/uninstall/uninstalling-explorer-server.md)
    * [Uninstalling Zoe Brightside](installandconfig/uninstall/cli-uninstallcli.md)
* [Using Project Zoe](using/README.md)
  * [Using zLUX](using/usingmvd/README.md)
    * [Navigating MVD](using/usingmvd/navigatingmvd.md)
    * [Using Explorers within zLUX](using/usingmvd/atlas-usingwebuiwithinmvd.md)
    * [Using zLUX application plug-ins](using/usingmvd/mvd-appplugins.md)
    * [zLUX logging](using/usingmvd/mvd-zluxlogging.md)
  * [Using APIs](using/usingapis/README.md)
    * [Using explorer server REST APIs](using/usingapis/atlas-usingatlasrestapis/README.md)
      * [Data set APIs](using/usingapis/atlas-usingatlasrestapis/atlas-datasetapis.md)
      * [Job APIs](using/usingapis/atlas-usingatlasrestapis/atlas-jobapis.md)
      * [Persistent Data APIs](using/usingapis/atlas-usingatlasrestapis/atlas-persistentdataapis.md)
      * [System APIs](using/usingapis/atlas-usingatlasrestapis/atlas-systemapi.md)
      * [USS File APIs](using/usingapis/atlas-usingatlasrestapis/atlas-ussfileapis.md)
      * [z/OS System APIs](using/usingapis/atlas-usingatlasrestapis/atlas-systemapis.md)
      * [Programming explorer server REST APIs](using/usingapis/atlas-usingatlasrestapis/atlas-programrestapi/README.md)
        * [Sending a GET request in Java](using/usingapis/atlas-usingatlasrestapis/atlas-programrestapi/atlas-getrequestinjava.md)
        * [Sending a GET request in JavaScript](using/usingapis/atlas-usingatlasrestapis/atlas-programrestapi/atlas-getrequestsinjavascript.md)
        * [Sending a POST request in JavaScript](using/usingapis/atlas-usingatlasrestapis/atlas-programrestapi/atlas-postrequestinjavascript.md)
        * [Explorer API sample in JavaScript](using/usingapis/atlas-usingatlasrestapis/atlas-programrestapi/atlas-extendedapisample.md)
    * [Using explorer server WebSocket services](using/usingapis/atlas-websocket.md)
  * [Using Zoe Brightside](using/cli-usingcli/README.md)
    * [How to display Zoe Brightside help](using/cli-usingcli/cli-howtodisplaybrightsidehelp.md)
    * [Zoe Brightside command groups](using/cli-usingcli/cli-commandgroups.md)
* [Extending Project Zoe](zoe_extending/README.md)
  * [Extending zLUX](zoe_extending/mvd-extendingzlux/README.md)
    * [Creating zLUX application plug-ins](zoe_extending/mvd-extendingzlux/mvd-plugincreateappplugin/README.md)
      * [Setting environment variables for plug-in development](zoe_extending/mvd-extendingzlux/mvd-plugincreateappplugin/mvd-pluginsetenvvars.md)
      * [Using the zLUX sample application plug-in](zoe_extending/mvd-extendingzlux/mvd-plugincreateappplugin/mvd-pluginexpsampapp.md)
    * [zLUX plug-in definition and structure](zoe_extending/mvd-extendingzlux/mvd-zluxplugindefandstruct/README.md)
      * [Plug-in filesystem structure](zoe_extending/mvd-extendingzlux/mvd-zluxplugindefandstruct/mvd-zluxpluginfilesystem.md)
      * [Location of plug-in files](zoe_extending/mvd-extendingzlux/mvd-zluxplugindefandstruct/mvd-pluginsdir.md)
      * [Plug-in definition file](zoe_extending/mvd-extendingzlux/mvd-zluxplugindefandstruct/mvd-plugindeffile.md)
      * [Plug-in attributes](zoe_extending/mvd-extendingzlux/mvd-zluxplugindefandstruct/mvd-pluginattributes.md)
    * [zLUX application filesystem structure](zoe_extending/mvd-extendingzlux/mvd-zluxappfilesystem.md)
    * [zLUX dataservices](zoe_extending/mvd-extendingzlux/mvd-zluxdataservices.md)
    * [Desktop and window management](zoe_extending/mvd-extendingzlux/mvd-desktopandwindowmgt.md)
    * [Configuration Dataservices](zoe_extending/mvd-extendingzlux/mvd-configdataservice/README.md)
      * [Resource Scope](zoe_extending/mvd-extendingzlux/mvd-configdataservice/mvd-resourcescope.md)
      * [REST API](zoe_extending/mvd-extendingzlux/mvd-configdataservice/mvd-restapi.md)
      * [Application API](zoe_extending/mvd-extendingzlux/mvd-configdataservice/mvd-appapi.md)
      * [Internal and bootstrapping](zoe_extending/mvd-extendingzlux/mvd-configdataservice/mvd-internalandbootstrap.md)
      * [Plug-in definition](zoe_extending/mvd-extendingzlux/mvd-configdataservice/mvd-cfgdataplugindef.md)
      * [Aggregation policies](zoe_extending/mvd-extendingzlux/mvd-configdataservice/mvd-aggregatepolicies.md)
    * [URI Broker](zoe_extending/mvd-extendingzlux/mvd-uribroker.md)
    * [Logging utility](zoe_extending/mvd-extendingzlux/mvd-logutility.md)
  * [Extending Zoe Brightside](zoe_extending/cli-extending/README.md)
    * [Installing plug-ins](zoe_extending/cli-extending/cli-installplugins.md)
    * [Zoe Brightside plug-in for IBM Db2 Database](zoe_extending/cli-extending/cli-db2plugin.md)
* [Notices](notices_toc/README.md)
  * [IBM notices](notices_toc/atlas-notices.md)
  * [Rocket Software notices](notices_toc/mvd-zluxlegalnotices.md)
  * [CA notices](notices_toc/cli-legalnotices.md)
