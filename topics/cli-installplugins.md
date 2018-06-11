# Install Plug-ins 

Use commands in the plugins command group to install and manage plug-ins for Zoe Brightside.

**Important!** Plug-ins can gain control of your CLI application
legitimately during the execution of every command. Install third-party
plug-ins at your own risk. CA Technologies makes no warranties regarding
the use of third-party plug-ins.

  - [Set the Registry](#InstallPlug-ins-SettheRegistry)
  - [Meet the Prerequisites](#InstallPlug-ins-MeetthePrerequisites)
  - [Validate Plug-ins](#InstallPlug-ins-ValidatePlug-ins)
  - [Update Plug-ins](#InstallPlug-ins-UpdatePlug-ins)
  - [Uninstall Plug-ins](#InstallPlug-ins-UninstallPlug-ins)

## Set the Registry

Before you install or update plug-ins, direct NPM to target the Zoe Brightside registry by issuing the following command: 

```
npm config set @brightside:registry https://api.bintray.com/npm/ca/brightside
```

The following plug-ins are available to install from the Zoe Brightside registry:

  - **CA Endevor**  
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
the plug-in to Zoe Brightside. For documentation related to each plug-in,
see [Extending](cli-extending.md).

## Install Plug-ins

Issue an `install `command to install plug-ins to Zoe Brightside. The
`install` command contains the following syntax:

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

```
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
  
    
    **Tip:** You can install multiple plug-ins with one command. For
    example, issue `bright plugin install plugin1 plugin2 plugin3`
    

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
integrate with Zoe Brightside. 

Perform
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