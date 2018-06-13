<div id="page">

<div id="main" class="aui-page-panel">

<div class="aui-page-panel-nav">

<div class="aui-navgroup-inner">

<div id="tabs-nav" class="aui-tabs horizontal-tabs">

  - [**Contents**](#tabs-navigation)
  - [**Search**](#tabs-search)

<div id="tabs-navigation" class="tabs-pane active-pane" data-current-page-id="473021289">

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
2.  <span> [Installing](Installing_473021284.html)
</span>

</div>

# <span id="title-text"> CA Brightside Community Edition : Install CA Brightside </span>

</div>

<div id="content" class="view">

<div class="page-metadata">

</div>

<div id="main-content" class="wiki-content group">

As a systems programmer or application developer, you install CA
Brightside on your
PC.

<div class="confluence-information-macro confluence-information-macro-warning">

<span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Important\!** Before you can use CA Brightside to interact with the
mainframe, systems programmers must install and configure IBM z/OSMF in
your mainframe environment. The IBM z/OS Management Facility guide on
the IBM Knowledge Center is the primary source of information about how
systems programmers can install and configure z/OSMF. We provide
supplemental information about CA Brightside-specific tips or
requirements to which systems programmers can refer. For more
information, see [z/OSMF Configuration Overview](473021286.html).

</div>

</div>

<div class="toc-macro rbtoc1528725935950">

  - [Install CA Brightside](#InstallCABrightside-Installbscli)
  - [Update CA Brightside](#InstallCABrightside-Updatebscli)

</div>

## Install CA Brightside

Install CA Brightside on PCs that are running a Windows, Linux, or macOS
operating system.

**Follow these steps:**

1.  <span>[Address the
    Prerequisites.](Prerequisites_473021285.html)</span>

2.  Open a command line window. For example, Windows Command Prompt.

3.  Issue the following command to set the registry to the CA Brightside
    scoped package on
    Bintray:
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    npm config set @brightside:registry https://api.bintray.com/npm/ca/brightside
    ```
    
    </div>
    
    </div>

4.  Issue the following command to install CA Brightside from the
    registry:
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    npm install -g @brightside/core@next
    ```
    
    </div>
    
    </div>
    
    <div class="confluence-information-macro confluence-information-macro-note">
    
    <span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>
    
    <div class="confluence-information-macro-body">
    
    **Note:** On Linux systems, you might need to append `sudo` to your
    `npm` commands so that you can issue the install and uninstall
    commands. For more information, see [Known
    Issues](Release-Notes_473021281.html#ReleaseNotes-knownIssues).
    
    </div>
    
    </div>
    
    CA Brightside is installed on your PC.

5.  Create a `zosmf` profile so that you can issue commands that
    communicate with
    z/OSMF.
    
    <div class="confluence-information-macro confluence-information-macro-note">
    
    <span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>
    
    <div class="confluence-information-macro-body">
    
    **Note:** For information about how to create a profile, see [Create
    a
    Profile](Create-a-Profile_473021290.html).
    
    </div>
    
    </div>
    
    <div class="confluence-information-macro confluence-information-macro-tip">
    
    <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"></span>
    
    <div class="confluence-information-macro-body">
    
    **Tip:** CA Brightside profiles contain information that is required
    for the product to interact with remote systems. For example, host
    name, port, and user ID. Profiles let you target unique systems,
    regions, or instances for a command. Most CA Brightside [command
    groups](Command-Groups_473021296.html) require a CA Brightside
    `zosmf` profile.
    
    </div>
    
    </div>

After you install and configure CA Brightside, you can issue the `bright
--help` command to view a list of available commands. For more
information, see [Display Help](Display-Help_473021295.html).

## Update CA Brightside

CA Brightside will have periodic updates. You can update CA Brightside
to the next version (for example, update from Version 2.0 to Release
2.1) or the latest version. You can identify your current version and
apply updates using the command
line.

<div class="confluence-information-macro confluence-information-macro-tip">

<span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Tip:** To identify the version of CA Brightside that is currently
installed on your PC, issue the following command:

`bright -V`

</div>

</div>

**Follow these steps:**

1.  Open a command line window and change to the directory where CA
    Brightside is installed.

2.  If you *did not* set the registry the first time that you installed
    CA Brightside, issue the following command to set the registry to
    the CA Brightside scoped package on
    Bintray:
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    npm config set @brightside:registry https://api.bintray.com/npm/ca/brightside
    ```
    
    </div>
    
    </div>

3.  Issue the following command to update CA
    Brightside: 
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    npm install -g @brightside/core@next
    ```
    
    </div>
    
    </div>
    
    <div class="confluence-information-macro confluence-information-macro-tip">
    
    <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"></span>
    
    <div class="confluence-information-macro-body">
    
    **Tip:** To update CA Brightside to a specific version, replace
    `next` with the version number as illustrated by the following
    example:
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    npm install -g @brightside/core@1.03.4
    ```
    
    </div>
    
    </div>
    
    </div>
    
    </div>

4.  (Optional) To confirm that the update was successful, issue the
    following command to display the version of CA Brightside that you
    installed on your
PC:
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    bright -V
    ```
    
    </div>
    
    </div>

<div class="confluence-information-macro confluence-information-macro-information">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**More Information:**

  - [Uninstall CA Brightside](Uninstall-CA-Brightside_473021293.html)

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
