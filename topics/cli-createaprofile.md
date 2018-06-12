<div id="page">

<div id="main" class="aui-page-panel">

<div class="aui-page-panel-nav">

<div class="aui-navgroup-inner">

<div id="tabs-nav" class="aui-tabs horizontal-tabs">

  - [**Contents**](#tabs-navigation)
  - [**Search**](#tabs-search)

<div id="tabs-navigation" class="tabs-pane active-pane" data-current-page-id="473021290">

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

# <span id="title-text"> CA Brightside Community Edition : Create a Profile </span>

</div>

<div id="content" class="view">

<div class="page-metadata">

</div>

<div id="main-content" class="wiki-content group">

Profiles are a CA Brightside function that lets you store configuration
information for use on multiple commands. You can create a profile that
contains your username, password, and connection details for a
particular mainframe system, then reuse that profile to avoid typing it
again on every command. You can switch between profiles to quickly
target different mainframe
subsystems.

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Important\!** A  `zosmf` profile is required to issue most CA
Brightside commands. The first profile that you create becomes your
default profile. When you issue any command that requires
a `zosmf` profile, the command executes using your default profile
unless you specify a specific profile name on that command.

</div>

</div>

**Follow these steps:**

1.  To create a `zosmf` profile, issue the following command. Refer to
    the available options in the help text to define your profile:
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    bright profiles create zosmf-profile --help
    ```
    
    </div>
    
    </div>

After you create a profile, verify that it can communicate with z/OSMF.
For more information, see [Test Connection to z/OSMF](473021291.html).

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
