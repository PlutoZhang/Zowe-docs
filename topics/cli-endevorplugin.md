<div id="page">

<div id="main" class="aui-page-panel">

<div class="aui-page-panel-nav">

<div class="aui-navgroup-inner">

<div id="tabs-nav" class="aui-tabs horizontal-tabs">

  - [**Contents**](#tabs-navigation)
  - [**Search**](#tabs-search)

<div id="tabs-navigation" class="tabs-pane active-pane" data-current-page-id="475935700">

</div>

<div id="tabs-search" class="tabs-pane">

</div>

</div>

</div>

</div>

<div class="section aui-page-panel-content">

<div id="main-header">

<div id="breadcrumb-section">

1.  <span> [CA Brightside Community Edition](index.html) </span>
2.  <span> [Extending](Extending_475935698.html)
</span>

</div>

# <span id="title-text"> CA Brightside Community Edition : CA Brightside Plug-in for CA Endevor SCM </span>

</div>

<div id="content" class="view">

<div class="page-metadata">

</div>

<div id="main-content" class="wiki-content group">

As a modern application developer or DevOps Admin, you need to be able
to script DevOps processes using a command-line interface (CLI).

Core CLI functions have traditionally been built around the lifecycle
capabilities in tools like CA Brightside Community Edition. Using the CA
Brightside Community Edition plugin for CA Brightside, developers and
DevOps admins can incorporate existing automation into CI/CD workflows,
and leverage WHAT from their laptop or integrated development
environment (IDE). CA Brightside brings together several environments
within a single interface, and enables efficient, streamlined
development by removing much of the usual need to switch between
different environments when you create a single code package.

The CA Brightside Community Edition plug-in for CA Endevor
SCM allows you to perform commands on multiple mainframe applications
at once from one terminal window, without the need to establish several
mainframe sessions. This environment provides you with
extensive functionality while saving technical and time resources.

CA Brightside enables you to perform the following actions using the CA
Brightside Community Edition plug-in without having to step out of the
CA Brightside interface:

  - Build code and integrate CA Brightside Community Edition element
    code into wider packages. 
  - Live interaction between several data sources within a single CLI
    that enables quick comparison and inclusion of data. 
  - Interact with CA Brightside Community Edition for basic SCM
    inventory, providing a more modern interface experience for end
    users, which enables easier learning and adoption, especially for
    users previously unfamiliar with CA Brightside Community Edition.

<div class="toc-macro rbtoc1528725936371">

  - [Prerequisites](#CABrightsidePlug-inforCAEndevorSCM-Prerequisites)
  - [CA Endevor Plugin for CA
    Brightside](#CABrightsidePlug-inforCAEndevorSCM-CAEndevorPluginforCABrightside)
  - [Use Cases](#CABrightsidePlug-inforCAEndevorSCM-UseCases)
  - [CA Brightside
    Commands](#CABrightsidePlug-inforCAEndevorSCM-CABrightsideCommands)

</div>

## Prerequisites

  - CA Brightside installed and configured. For more information,
    see [Install CA Brightside](Install-CA-Brightside_473021289.html).
  - CA Brightside Community Edition instance configured within Endevor
    web services.
  - Endevor web services installed and running.

## CA Endevor Plugin for CA Brightside

To install the CA Brightside plug-in, see [Install
Plug-ins](Install-Plug-ins_473021292.html).

## Use Cases

  - <span style="color: rgb(0,0,0);">Brightside commands interact
    with CA Brightside Community Edition build actions, enabling more
    modern interaction with CA Brightside Community
    Edition.</span><span style="color: rgb(0,0,0);"> </span>
  - <span style="color: rgb(0,0,0);">Brightside commands interact
    with CA Brightside Community Edition application lifecycle actions,
    allowing easy scripting from CI/CD
    pipelines.</span><span style="color: rgb(0,0,0);"> </span><span style="color: rgb(0,0,0);"> </span>
  - <span style="color: rgb(0,0,0);">Enables developers to interact
    with CA Brightside Community Edition for basic SCM inventory
    actions using the CLI which provides an alternate, more UX friendly
    interface.</span>
  - Enables interaction between CA Brightside Community
    Edition including ACL and REST API, and CA FileMaster Plus within a
    single CLI<span style="color: rgb(0,0,0);"> </span>
  - Check out/check in of source code assets to a remote location for
    use within a non-mainframe IDE or editor (for example, Sublime,
    Visual Studio Code, IntelliJ IDEA)
  - Build of checked in source for use in unit & functional test
    environments
  - Code packaging and promotion as part of a CI/CD pipeline
  - Approval workflows in response to events in other DevOps tools

## CA Brightside Commands

To obtain a current list of the CA Endevor syntax, actions, and options,
open CA Brightside and enter the following command:

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
bright endevor -h
```

</div>

</div>

</div>

</div>

</div>

</div>

  - <span id="n-473021279">[CA Brightside Community
    Edition](index.html)</span>
      - <span id="n-473021281">[Release
        Notes](Release-Notes_473021281.html)</span>
    <!-- end list -->
      - <span id="n-473021284">[Installing](Installing_473021284.html)</span>
          - <span id="n-473021285">[Prerequisites](Prerequisites_473021285.html)</span>
        <!-- end list -->
          - <span id="n-473021286">[z/OSMF Configuration
            Overview](473021286.html)</span>
              - <span id="n-473021287">[Configure
                z/OSMF](473021287.html)</span>
            <!-- end list -->
              - <span id="n-473021288">[Configure z/OSMF
                Security](473021288.html)</span>
        <!-- end list -->
          - <span id="n-473021289">[Install CA
            Brightside](Install-CA-Brightside_473021289.html)</span>
        <!-- end list -->
          - <span id="n-473021290">[Create a
            Profile](Create-a-Profile_473021290.html)</span>
        <!-- end list -->
          - <span id="n-473021291">[Test Connection to
            z/OSMF](473021291.html)</span>
        <!-- end list -->
          - <span id="n-473021293">[Uninstall CA
            Brightside](Uninstall-CA-Brightside_473021293.html)</span>
    <!-- end list -->
      - <span id="n-475935698">[Extending](Extending_475935698.html)</span>
          - <span id="n-473021292">[Install
            Plug-ins](Install-Plug-ins_473021292.html)</span>
        <!-- end list -->
          - <span id="n-475935700">[CA Brightside Plug-in for CA Endevor
            SCM](CA-Brightside-Plug-in-for-CA-Endevor-SCM_475935700.html)</span>
        <!-- end list -->
          - <span id="n-475935701">[CA Brightside Plug-in for CA File
            Master
            Plus](CA-Brightside-Plug-in-for-CA-File-Master-Plus_475935701.html)</span>
        <!-- end list -->
          - <span id="n-475943406">[CA Brightside Plug-in for IBM Db2
            Database](CA-Brightside-Plug-in-for-IBM-Db2-Database_475943406.html)</span>
    <!-- end list -->
      - <span id="n-473021294">[Using](Using_473021294.html)</span>
          - <span id="n-473021295">[Display
            Help](Display-Help_473021295.html)</span>
        <!-- end list -->
          - <span id="n-473021296">[Command
            Groups](Command-Groups_473021296.html)</span>
    <!-- end list -->
      - <span id="n-473021297">[Additional
        Resources](Additional-Resources_473021297.html)</span>
    <!-- end list -->
      - <span id="n-38207495">[Legal
        Notices](Legal-Notices_38207495.html)</span>

<div id="footer">

<div class="section footer-body">

Copyright © 2018 CA. All rights reserved.

<div class="footer-logo">

</div>

Document generated on Jun 11, 2018 10:05.

</div>

</div>

</div>
