<div id="page">

<div id="main" class="aui-page-panel">

<div class="aui-page-panel-nav">

<div class="aui-navgroup-inner">

<div id="tabs-nav" class="aui-tabs horizontal-tabs">

  - [**Contents**](#tabs-navigation)
  - [**Search**](#tabs-search)

<div id="tabs-navigation" class="tabs-pane active-pane" data-current-page-id="473021293">

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

# <span id="title-text"> CA Brightside Community Edition : Uninstall CA Brightside </span>

</div>

<div id="content" class="view">

<div class="page-metadata">

</div>

<div id="main-content" class="wiki-content group">

You can uninstall CA Brightside when you no longer want to use the
product.

<div class="confluence-information-macro confluence-information-macro-warning">

<span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Important\!** The uninstall process does not delete the profiles and
credentials that you created when using the product from your PC. To
delete the profiles from your PC, delete them before you uninstall CA
Brightside.

</div>

</div>

The following steps describe how to list the profiles that you created,
delete the profiles, and uninstall CA Brightside.

**Follow these steps:**

1.  Open a command line
    window. 
    
    <div class="confluence-information-macro confluence-information-macro-note">
    
    <span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>
    
    <div class="confluence-information-macro-body">
    
    **Note:** If you do not want to delete the CA Brightside profiles
    from your PC, go to Step 5.
    
    </div>
    
    </div>

2.  List all profiles that you created for a [Command
    Group](Command-Groups_473021296.html) by issuing the following
    command:
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    bright profiles list <profileType>
    ```
    
    </div>
    
    </div>
    
    **Example:**
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    $ bright profiles list zosmf
    The following profiles were found for the module zosmf:
    'SMITH-123' (DEFAULT)
    smith-123@SMITH-123-W7 C:\Users\SMITH-123
    $
    ```
    
    </div>
    
    </div>

3.  Delete all of the profiles that are listed for the command group by
    issuing the following
    command: 
    
    <div class="confluence-information-macro confluence-information-macro-tip">
    
    <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"></span>
    
    <div class="confluence-information-macro-body">
    
    **Tip:** For this command, use the results of the `list`
    command.
    
    </div>
    
    </div>
    
    <div class="confluence-information-macro confluence-information-macro-note">
    
    <span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>
    
    <div class="confluence-information-macro-body">
    
    **Note:** When you issue the `delete` command, it deletes the
    specified profile and its credentials from the credential vault in
    your PC's operating system.
    
    </div>
    
    </div>
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    bright profiles delete <profileType> <profileName> --force  
    ```
    
    </div>
    
    </div>
    
    **Example:**
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    bright profiles delete zosmf SMITH-123 --force
    ```
    
    </div>
    
    </div>

4.  Repeat Steps 2 and 3 for all CA Brightside command groups and
    profiles.

5.  Uninstall CA Brightside by issuing the following command:
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    npm uninstall --global @brightside/core
    ```
    
    </div>
    
    </div>
    
    The uninstall process removes all CA Brightside installation
    directories and files from your PC.

6.  Delete the following directory on your PC. The directory contains
    the CA Brightside log files and other miscellaneous files that were
    generated when you used the
    product.
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    C:\Users\<user_name>\.brightside
    ```
    
    </div>
    
    </div>
    
    <div class="confluence-information-macro confluence-information-macro-tip">
    
    <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"></span>
    
    <div class="confluence-information-macro-body">
    
    **Tip:** Deleting the `C:\Users\<user_name>\.brightside` directory
    does not harm your PC.
    
    </div>
    
    </div>

7.  Issue the following command to clear your scoped
npm registry:
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    npm config set @brightside:registry
    ```
    
    </div>
    
    </div>

<div class="confluence-information-macro confluence-information-macro-information">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**More Information:**

  - [Install CA Brightside](Install-CA-Brightside_473021289.html)

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
