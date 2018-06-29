# User's Guide

-   [Edition notice](topics/editionnotice.md)
-   [About this guide](topics/aboutthisbook.md)
-   [Summary of changes](topics/summaryofchanges.md)
-   [Known issues](knownissues.md)
-   [Project Zoe overview](topics/zoe-introduction.md)
      - [zLUX](topics/mvd-overview.md)
      - [Explorer server](topics/atlas-overview.md)
      - [Zoe Brightside](topics/cli-releasenotes.md)
-   [Installing Project Zoe](topics/installandconfig.md)
    -  [Installation roadmap](topics/installroadmap.md)
    -  [System requirements](topics/planinstall.md)
        -   [z/OSMF configuration](topics/prezosmf.md)
        -   [System requirements for zLUX](topics/premvd.md)
            -   [Confirming that Node.js is installed](topics/mvd-instconfirmnodejsinstalled.md)
            -   [Configuring ports for the zLUX terminal application plug-ins](topics/mvd-configterminalappports.md)
        -   [System requirements for explorer server](topics/atlas-prereqs.md)
        -   [System requirements for Zoe Brightside](topics/cli-precli.md)
    -  [Obtaining installation files](topics/zoegettingstarted.md)
    -  [Installing zLUX and explorer server](topics/zoeinstall-zos.md)
        -   [Installing Zoe runtime on z/OS](topics/zoeinstall.md)
        -   [Starting and stopping the Zoe runtime on z/OS](topics/zoestartstop.md)
        -   [Verifying installation](topics/verify.md)
            - [Verifying zLUX installation](topics/mvd-instopendesktopbrowser.md)
              -   [Setting up the terminal application plug-ins](topics/mvd-settingupterminalapps.md)
            - [Verifying explorer server installation](topics/atlas-verifyinstall.md)
        -   [Troubleshooting installing the Zoe runtime](topics/zoeinstalltroubleshoot.md)
            -   [Troubleshooting installing zLUX](topics/mvd-troubleshoot.md)
            -   [Troubleshooting installing explorer server](topics/atlas-troubleshoot.md)
    -  [Installing Zoe Brightside](topics/cli-installcli.md)
        -  [Creating a Zoe Brightside profile](topics/cli-createaprofile.md)
        -  [Verifying Zoe Brightside connection to z/OSMF](topics/cli-validateInstallation.md)
        -  [Troubleshooting installing Zoe Brightside](topics/cli-troubleshootinginstallingcli.md)          
    -   [Uninstalling Project Zoe](topics/uninstall.md)
        -   [Uninstalling zLUX](topics/mvd-uninstallingzlux.md)
        -   [Uninstalling explorer server](topics/atlas-uninstall)
        -   [Uninstalling Zoe Brightside](topics/cli-uninstallcli.md)
-   [Using Project Zoe](topics/using.md)
    -   [Using zLUX](topics/usingmvd.md)
        - [Navigating MVD](topics/navigatingmvd.md)
        - [Using Explorers within zLUX](topics/atlas-usingwebuiwithinmvd.md)
        - [Using zLUX application plug-ins](topics/mvd-appplugins.md)
        - [zLUX logging](topics/mvd-zluxlogging.md)
    -   [Using APIs](topics/usingapis.md)
        -   [Using explorer server REST APIs](topics/atlas-usingatlasrestapis.md)
            -   [Data set APIs](topics/atlas-datasetapis.md)
            -   [Job APIs](topics/atlas-jobapis.md)
            -   [Persistent Data APIs](topics/atlas-persistentdataapis.md)
            -   [System APIs](topics/atlas-systemapi.md)
            -   [USS File APIs](topics/atlas-ussfileapis.md)
            -   [z/OS System APIs](topics/atlas-systemapis.md)
            -   [Programming explorer server REST APIs](topics/atlas-programrestapi.md)
                - [Sending a GET request in Java](topics/atlas-getrequestinjava.md)
                - [Sending a GET request in JavaScript](topics/atlas-getrequestsinjavascript.md)
                - [Sending a POST request in JavaScript](topics/atlas-postrequestinjavascript.md)
                - [Explorer API sample in JavaScript](topics/atlas-extendedapisample.md)
        -   [Using explorer server WebSocket services](topics/atlas-websocket.md)
            -   [Programming explorer server WebSocket services](topics/atlas-programwebsocket.md)
    -   [Using Zoe Brightside](topics/cli-usingcli.md)
        -  [How to display Zoe Brightside help](topics/cli-howtodisplaybrightsidehelp.md)
        -  [Zoe Brightside command groups](topics/cli-commandgroups.md)
-  [Extending Project Zoe](topics/zoe_extending.md)
     - [Extending Zoe Brightside](topics/cli-extending.md)
        - [Installing plug-ins](topics/cli-installplugins.md)
        - [Zoe Brightside plug-in for CA Endevor SCM](topics/cli-endevorplugin.md)
        - [Zoe Brightside plug-in for CA File Master Plus](topics/cli-fmpplugin.md)
        - [Zoe Brightside plug-in for IBM Db2 Database](topics/cli-db2plugin.md)
     - [Extending zLUX](topics/mvd-extendingzlux.md)  
        - [Creating zLUX application plug-ins](topics/mvd-plugincreateappplugin.md)
          -   [Setting environment variables for plug-in development](topics/mvd-pluginsetenvvars.md)
          -   [Using the zLUX sample application plug-in](topics/mvd-pluginexpsampapp.md)
        - [zLUX plug-in definition and structure](topics/mvd-zluxplugindefandstruct.md)
          -   [Plug-in filesystem structure](topics/mvd-zluxpluginfilesystem.md)
          -   [Location of plug-in files](topics/mvd-pluginsdir.md)
          -   [Plug-in definition file](topics/mvd-plugindeffile.md)
          -   [Plug-in attributes](topics/mvd-pluginattributes.md)  
        - [zLUX application filesystem structure](topics/mvd-zluxappfilesystem.md)
        - [zLUX dataservices](topics/mvd-zluxdataservices.md)   
        - [Desktop and window management](topics/mvd-desktopandwindowmgt.md)     
        - [Configuration Dataservices](topics/mvd-configdataservice.md)
          -   [Resource Scope](topics/mvd-resourcescope.md)
          -   [REST API](topics/mvd-restapi.md)
          -   [Application API](topics/mvd-appapi.md)
          -   [Internal and bootstrapping](topics/mvd-internalandbootstrap.md)
          -   [Plug-in definition](topics/mvd-cfgdataplugindef.md)
          -   [Aggregation policies](topics/mvd-aggregatepolicies.md) 
        - [Configuring the zLUX Proxy Server and ZSS](topics/mvd-configzluxproxyandzss.md)
        - [URI Broker](topics/mvd-uribroker.md)
        - [Logging utility](topics/mvd-logutility.md)
-  [Notices](topics/notices_toc.md)
    -  [IBM notices](topics/atlas-notices.md)
    -  [Rocket Software notices](topics/mvd-zluxlegalnotices.md)
    -  [CA notices](topics/cli-legalnotices.md)
