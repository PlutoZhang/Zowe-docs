<div id="page">

<div id="main" class="aui-page-panel">

<div class="aui-page-panel-nav">

<div class="aui-navgroup-inner">

<div id="tabs-nav" class="aui-tabs horizontal-tabs">

  - [**Contents**](#tabs-navigation)
  - [**Search**](#tabs-search)

<div id="tabs-navigation" class="tabs-pane active-pane" data-current-page-id="473021292">

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

# <span id="title-text"> CA Brightside Community Edition : Install Plug-ins </span>

</div>

<div id="content" class="view">

<div class="page-metadata">

</div>

<div id="main-content" class="wiki-content group">

<span style="color: rgb(36,41,46);">Use commands in
the </span>`plugins`<span style="color: rgb(36,41,46);"> command group
to install and manage plug-ins for </span>CA
Brightside<span style="color: rgb(36,41,46);">.</span>

<div class="confluence-information-macro confluence-information-macro-warning">

<span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Important\!** <span>Plug-ins can gain control of your CLI application
legitimately during the execution of every command. Install third-party
plug-ins at your own risk. CA Technologies makes no warranties regarding
the use of third-party plug-ins.</span>

</div>

</div>

<div class="toc-macro rbtoc1528725936194">

  - [Set the Registry](#InstallPlug-ins-SettheRegistry)
  - [Meet the Prerequisites](#InstallPlug-ins-MeetthePrerequisites)
  - [Validate Plug-ins](#InstallPlug-ins-ValidatePlug-ins)
  - [Update Plug-ins](#InstallPlug-ins-UpdatePlug-ins)
  - [Uninstall Plug-ins](#InstallPlug-ins-UninstallPlug-ins)

</div>

## <span style="font-size: 20.0px;">Set the Registry</span>

Before you install or update plug-ins, direct NPM to target the CA
Brightside registry by issuing the following
command: 

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
npm config set @brightside:registry https://api.bintray.com/npm/ca/brightside
```

</div>

</div>

The following plug-ins are available to install from the CA
Brightside registry:

  - **CA Endevor **  
    Use `@brightside/endevor` in your command syntax to install, update,
    and validate the CA Endevor plug-in. 
  - **CA File Master Plus**  
    Use `@brightside/filemasterplus` in your command syntax to install,
    update, and validate the CA File Master Plus plug-in. 
  - **IBM Db2 Database**  
    Use `@brightside/db2` in your command syntax to install, update, and
    validate the IBM Db2 Database plug-in. 

## Meet the Prerequisites

Ensure that you meet the prerequisites for a plug-in before you install
the plug-in to CA Brightside. For documentation related to each plug-in,
see [Extending](Extending_475935698.html).

<span style="font-size: 20.0px;">Install Plug-ins</span>

Issue an `install `command to install plug-ins to CA Brightside. The
`install` command contains the following syntax:

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
bright plugins install [plugin...] [--registry <registry>]
```

</div>

</div>

  - **`[plugin...]`**   
    (Optional) Specifies the name of a plug-in, an npm package, or a
    pointer to a (local or remote) URL. When you do not specify a
    plug-in version, the command installs the latest plug-in version and
    specifies the prefix that is stored in npm save-prefix. For more
    information, see [npm save
    prefix](https://docs.npmjs.com/misc/config#save-prefix). For more
    information about npm semantic versioning, see [npm
    semver](https://docs.npmjs.com/misc/semver). Optionally, you can
    specify a specific version of a plug-in to install. For example,`
    bright plugin install
    pluginName@^1.0.0`.
    
    <div class="confluence-information-macro confluence-information-macro-tip">
    
    <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"></span>
    
    <div class="confluence-information-macro-body">
    
    **Tip:** You can install multiple plug-ins with one command. For
    example, issue `bright plugin install plugin1 plugin2 plugin3`
    
    </div>
    
    </div>

  - **`[--registry <registry>]`**  
    (Optional) Specifies a registry URL from which to install a plug-in
    when you do not use `npm config set` to set the registry initially. 

**<span style="color: rgb(36,41,46);">Examples: Install
Plug-ins</span>**

  - The following example illustrates the syntax to use to install a
    plug-in that is named "my-plugin" from a specified registry:
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    bright plugins install @brightside/my-plugin
    ```
    
    </div>
    
    </div>

  - The following example illustrates the syntax to use to install a
    specific version of "my-plugins" 
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
     bright plugins install @brightside/my-plugin@"^1.2.3"
    ```
    
    </div>
    
    </div>

## Validate Plug-ins

<span style="color: rgb(36,41,46);">Issue the plug-in validation command
to run tests against all plug-ins (or against a plug-in that you
specify) to verify that the plug-ins integrate properly with CA
Brightside . The tests confirm that the plug-in does not conflict with
existing command groups in the base application. The command response
provides you with details or error messages about how the plug-ins
integrate with CA
Brightside. </span>

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**<span style="color: rgb(36,41,46);">Note:</span>**<span style="color: rgb(36,41,46);"> Perform
validation after you install the plug-ins to help ensure that it
integrates with <span style="color: rgb(36,41,46);">CA
Brightside</span>.  
</span>

</div>

</div>

The `validate` command contains the following syntax:

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
bright plugins validate [plugin]
```

</div>

</div>

  - **`[plugin]`**  
    (Optional) Specifies the name of the plug-in that you want to
    validate. If you do not specify a plug-in name, the command
    validates all installed plug-ins. The name of the plug-in is not
    always the same as the name of the NPM package.

**<span style="color: rgb(36,41,46);">Examples: Validate
Plug-ins</span>**

  - The following example illustrates the syntax to use to validate a
    specified installed plug-in:
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    bright plugins validate @brightside/my-plugin
    ```
    
    </div>
    
    </div>

  - The following example illustrates the syntax to use to validate all
    installed plug-ins:
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    bright plugins validate
    ```
    
    </div>
    
    </div>

## Update Plug-ins

Issue the `update` command to install the latest version or a specific
version of a plug-in that you installed previously. The `update` command
contains the following syntax:

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
bright plugins update [plugin...] [--registry <registry>]
```

</div>

</div>

  - **`[plugin...]`** 
    
    Specifies the name of an installed plug-in that you want to update.
    The name of the plug-in is not always the same as the name of the
    NPM package. <span>You can use npm semantic versioning to specify a
    plug-in version to which to update. For more information,
    see </span>[npm
    semver](https://docs.npmjs.com/misc/semver)<span>.</span>

  - **`[--registry <registry>]`**
    
    (Optional) Specifies a registry URL that is different from the
    registry URL of the original installation. 

**<span style="color: rgb(36,41,46);">Examples: Update Plug-ins</span>**

  - The following example illustrates the syntax to use to update an
    installed plug-in to the latest version:
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    bright plugins update @brightside/my-plugin@next
    ```
    
    </div>
    
    </div>

  - The following example illustrates the syntax to use to update a
    plug-in to a specific version:
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    bright plugins update @brightside/my-plugin@"^1.2.3"
    ```
    
    </div>
    
    </div>

## Uninstall Plug-ins

Issue the `uninstall` command to uninstall plug-ins from a base
application. After the uninstall process completes successfully,
the product no longer contains the plug-in
configuration.

<div class="confluence-information-macro confluence-information-macro-tip">

<span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Tip:** The command is equivalent to using [npm
uninstall](https://docs.npmjs.com/cli/uninstall) to uninstall a package.

</div>

</div>

The `uninstall` command contains the following syntax:

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
bright plugins uninstall [plugin]
```

</div>

</div>

  - **`[plugin]`**   
    Specifies the plug-in name to uninstall.

**<span style="color: rgb(36,41,46);">Example: Uninstall
Plug-ins</span>**

  - The following example illustrates the syntax to use to uninstall a
    plug-in:
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    bright plugins uninstall @brightside/my-plugin
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
