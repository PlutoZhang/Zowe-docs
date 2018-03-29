# User's Guide

-   [Edition notice](topics/editionnotice.md)
-   [About this book](topics/aboutthisbook.md)
-   [Project Giza overview](topics/introduction.md)
    - [What is Project Giza](topics/whatis.md)
    - [Components overview](topics/componentoverview.md)
      - [zLux overview](topics/mvd-overview.md)
      - [Atlas overview](topics/atlas-overview.md)
      - [Brightside CLI Overview](topics/cli-releasenotes.md)
-   [Installing Project Giza](topics/installandconfig.md)
    -   [Planning for installation](topics/planinstall.md)
        -   [Prerequisites for z/OSMF configuration](topics/prezosmf.md)
        -   [Prerequisites for zLUX](topics/premvd.md)
            -   [Verifying that your system meets the software requirements](topics/mvd-verifysystemswreqs.md)
            -   [Confirming that Node.js is installed on the z/OS host](topics/mvd-instconfirmnodejsinstalled.md)
            -   [Verifying port number availability](topics/mvd-instverifyportnumavailable.md)
        -   [Prerequisites for Atlas](topics/atlas-prereqs.md)
        -   [Prerequisites for Brightside CLI](topics/precli.md)
    -   [Installing components of Project Giza](topics/installing.md)  
        -   [Installing zLUX](topics/installvirtualdesktop.md)
            -   [Setting up the Giza Node server and the ZSSAS on z/OS](topics/mvd-instsetupeverythingonzos.md)
            -   [Starting the zLUX servers](topics/mvd-startzluxserver.md)
        -   [Installing Atlas](topics/atlas-install.md)
        -   [Installing Brightside CLI](topics/cli-installcli.md)
    -   [Verifying installation](topics/verify.md)
        - [Verifying Atlas installation](topics/atlas-verifyinstall.md)
        - [Opening the MVD in a browser](topics/mvd-instopendesktopbrowser.md)
        - [Validating Brightside CLI installation](topics/cli-validateInstallation.md)
        - [Identify and correct problems detected by the validate profile command](topics/cli-validateInstallationcorrectproblems.md)
    -   [Uninstalling Project Giza](topics/uninstall.md)
        -   [Uninstalling zLUX](topics/mvd-uninstallingzlux.md)
        -   [Uninstalling Atlas](topics/atlas-uninstall)
        -   [Uninstalling Brightside CLI](topics/cli-uninstallcli.md)
    -   [Troubleshooting installation](topics/troubleshoot.md)
        -   [Troubleshooting installing zLUX](topics/mvd-troubleshoot.md)
        -   [Troubleshooting installing Atlas](topics/atlas-troubleshoot.md)
        -   [Troubleshooting installing Brightside CLI](topics/cli-troubleshootinginstallingcli.md)
-   [Using Project Giza](topics/using.md)
    -   [Using zLUX](topics/usingmvd.md)
        - [Navigating zLUX](topics/navigatingmvd.md)
        - [Using Atlas Explorers within zLUX](topics/atlas-usingwebuiwithinmvd.md)
        - [Creating an application plug-in](topics/mvd-plugincreateappplugin.md)
          -   [Setting environment variables for plug-in development](topics/mvd-pluginsetenvvars.md)
          -   [Experimenting with the zLUX sample application plug-in](topics/mvd-pluginexpsampapp.md)
    -   [Using APIs](topics/usingapis.md)
        -   [Using Atlas REST APIs](topics/atlas-usingatlasrestapis.md)
            -   [Dataset APIs](topics/atlas-datasetapis.md)
            -   [Job APIs](topics/atlas-jobapis.md)
            -   [Persistent Data APIs](topics/atlas-persistentdataapis.md)
            -   [System APIs](topics/atlas-systemapi.md)
            -   [USS File APIs](topics/atlas-ussfileapis.md)
            -   [z/OS System APIs](topics/atlas-systemapis.md)
            -   [Programming Atlas REST APIs](topics/atlas-programrestapi.md)
                - [Sending a GET request in Java](topics/atlas-getrequestinjava.md)
                - [Sending a GET request in JavaScript](topics/atlas-getrequestsinjavascript.md)
                - [Sending a POST request in JavaScript](topics/atlas-postrequestinjavascript.md)
                - [Extended API sample in JavaScript](topics/atlas-extendedapisample.md)
        -   [Using Atlas WebSocket services](topics/atlas-websocket.md)
            -   [Programming Atlas WebSocket services](topics/atlas-programwebsocket.md)
    -   [Using Brightside CLI](topics/cli-usingcli.md)
        -  [How to display Brightside CLI help](topics/cli-howtodisplaybrightsidehelp.md)
        -  [Brightside CLI Command groups](topics/cli-commandgroups.md)
        -  [Enabling and disabling experimental commands](topics/cli-enabledisablexperimentalcommands.md)
        -  [Brightside CLI scenarios](topics/cli-scenarios.md)
    -  [Legal information](topics/legal.md)
        -  [CA documentation legal notices](topics/cli-legalnotices.md)
        -  [Rocket Software legal notices](topics/mvd-zluxlegalnotices.md)
