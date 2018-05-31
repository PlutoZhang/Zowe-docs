# User's Guide

-   [Edition notice](topics/editionnotice.md)
-   [About this guide](topics/aboutthisbook.md)
-   [Summary of changes](topics/summaryofchanges.md)
-   [Known issues](knownissues.md)
-   [Project Zoe overview](topics/introduction.md)
    - [What is Project Zoe](topics/whatis.md)
    - [Components overview](topics/componentoverview.md)
      - [zLUX overview](topics/mvd-overview.md)
      - [Explorer server overview](topics/atlas-overview.md)
      - [Brightside CLI overview](topics/cli-releasenotes.md)
-   [Installing Project Zoe](topics/installandconfig.md)
    -  [Obtaining the Zoe runtime](topics/zoegettingstarted.md)
    -  [Prerequisites](topics/planinstall.md)
        -   [Prerequisites for z/OSMF configuration](topics/prezosmf.md)
        -   [Prerequisites for zLUX server](topics/premvd.md)
            -   [Confirming that Node.js is installed](topics/mvd-instconfirmnodejsinstalled.md)
        -   [Prerequisites for explorer server](topics/atlas-prereqs.md)
        -   [Prerequisites for Brightside CLI](topics/precli.md)
    -   [Installing Zoe runtime on z/OS](topics/zoeinstall.md)
    -   [Troubleshooting installing the Zoe runtime](topics/zoeinstalltroubleshoot.md)
    -   [Starting and stopping the Zoe runtime](topics/zoestartstop.md)
    -   [Setting up the terminal application plug-ins](topics/mvd-settingupterminalapps.md)
    -   [Installing Brightside CLI](topics/cli-installcli.md)
    -   [Verifying installation](topics/verify.md)
        - [Verifying zLUX installation](topics/mvd-instopendesktopbrowser.md)
        - [Verifying explorer server installation](topics/atlas-verifyinstall.md)
        - [Validating Brightside CLI installation](topics/cli-validateInstallation.md)
        - [Identifying and correcting problems detected by the validate profile command](topics/cli-validateInstallationcorrectproblems.md)
    -   [Troubleshooting installation](topics/troubleshoot.md)
        -   [Troubleshooting installing zLUX](topics/mvd-troubleshoot.md)
        -   [Troubleshooting installing explorer server](topics/atlas-troubleshoot.md)
        -   [Troubleshooting installing Brightside CLI](topics/cli-troubleshootinginstallingcli.md)
    -   [Uninstalling Project Zoe](topics/uninstall.md)
        -   [Uninstalling zLUX](topics/mvd-uninstallingzlux.md)
        -   [Uninstalling explorer server](topics/atlas-uninstall)
        -   [Uninstalling Brightside CLI](topics/cli-uninstallcli.md)
-   [Using Project Zoe](topics/using.md)
    -   [Using zLUX](topics/usingmvd.md)
        - [Navigating MVD](topics/navigatingmvd.md)
        - [Using Explorers within zLUX](topics/atlas-usingwebuiwithinmvd.md)
        - [Using zLUX application plug-ins](topics/mvd-appplugins.md)
        - [Creating zLUX application plug-ins](topics/mvd-plugincreateappplugin.md)
          -   [Setting environment variables for plug-in development](topics/mvd-pluginsetenvvars.md)
          -   [Using the zLUX sample application plug-in](topics/mvd-pluginexpsampapp.md)
        - [zLUX plug-in definition and structure](topics/mvd-zluxplugindefandstruct.md)
          -   [Plug-in filesystem structure](topics/mvd-zluxpluginfilesystem.md)
          -   [Location of plug-in files](topics/mvd-pluginsdir.md)
          -   [Plug-in definition file](topics/mvd-plugindeffile.md)
          -   [Plug-in attributes](topics/mvd-pluginattributes.md)  
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
    -   [Using Brightside CLI](topics/cli-usingcli.md)
        -  [How to display Brightside CLI help](topics/cli-howtodisplaybrightsidehelp.md)
        -  [Brightside CLI Command groups](topics/cli-commandgroups.md)
        -  [Enabling and disabling experimental commands](topics/cli-enabledisablexperimentalcommands.md)
        -  [Brightside CLI scenarios](topics/cli-scenarios.md)
-  [Notices](topics/notices_toc.md)
    -  [IBM notices](topics/atlas-notices.md)
    -  [Rocket Software notices](topics/mvd-zluxlegalnotices.md)
    -  [CA notices](topics/cli-legalnotices.md)
