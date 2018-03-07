#cInstall Brightside CLI </span>

</div>

<div id="content" class="view">

<div class="page-metadata">

</div>

<div id="main-content" class="wiki-content group">

As a systems programmer or application developer, you install Brightside
CLI on your personal computer. You can install Brightside CLI on any
personal computer that is running a Windows, Linux, macOS operating
system that supports Node.js version 6 or
later.

<div class="confluence-information-macro confluence-information-macro-warning">

<span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Important\!** Before you can use Brightside CLI to interact with the
mainframe, a systems programmer must install and configure IBM z/OSMF in
your environment. For more information about how systems programmers and
security administrators perform the z/OSMF configuration, see [Overview
of the z/OS Management Facility Configuration Process](433363261.html).

</div>

</div>

  

<div class="toc-macro rbtoc1519943043565">

  - [Install Brightside CLI](#InstallBrightsideCLI-Installbscli)
  - [Update Brightside CLI](#InstallBrightsideCLI-UpdateBrightsideCLI)
  - [Uninstall Brightside
    CLI](#InstallBrightsideCLI-UninstallBrightsideCLI)

</div>

## Install Brightside CLI

Node.js® is a JavaScript runtime environment on which we
architected Brightside CLI. You use the Node.js package manager (npm)
to install Brightside CLI. After you install Node.js, you can then
install Brightside CLI using the Node.js package
manager. 

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:**<span> CA Technologies does not maintain the prerequisite
software that </span>Brightside CLI<span> requires. You are responsible
for updating Node.js and other prerequisites on your PC. We recommend
that you update Node.js regularly to the latest Long Term Support (LTS)
version.</span>

</div>

</div>

<div class="confluence-information-macro confluence-information-macro-warning">

<span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Important\!** You might encounter problems when you attempt to install
Brightside CLI d<span>epending on your operating system and
environment.</span> For more information and workarounds, see [Known
Issues.](Release-Notes_417294291.html#ReleaseNotes-knownIssues)

</div>

</div>

**Follow these steps:**

1.  <span>Go to the *Installing Node.js via package manager* website at
    the following URL, and follow the instructions for installing
    Node.js on your operating
    system: </span>
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    https://nodejs.org/en/download/package-manager
    ```
    
    </div>
    
    </div>
    
      
    
    <div class="confluence-information-macro confluence-information-macro-tip">
    
    <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"></span>
    
    <div class="confluence-information-macro-body">
    
    **Tip:** If you are installing Node.js on a Linux or a macOS
    operating system, CA recommends that you install `nodejs` and
    `nodejs-legacy` using the instructions on the Nodejs website (using
    package manager). For example, you can install nodejs-legacy using
    the command `sudo apt install nodejs-legacy`. With `nodejs-legacy`,
    you can issue `node` commands rather than typing
    `nodejs`.<span style="color: rgb(255,0,0);"> </span>
    
    </div>
    
    </div>
    
    Node.js is installed on your PC.

2.  Download the Brightside CLI installation package from the
    **Downloads** section
    on [validate.ca.com.](https://validate.ca.com/project/version/item.html?cap=13283cc32fd9439c85aeb18bba4ac1f6&arttypeid=%7B4109d6e9-6c06-448b-8eb2-6601a5616391%7D&artid=%7B5ACC31C0-2176-437F-B06B-8C572D48C76C%7D)

3.  Open a command line window. Browse to the directory where you
    downloaded the Brightside CLI installation package. Issue the
    following command to install Brightside
    CLI:
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    npm install -g <file_name>
    ```
    
    </div>
    
    </div>
    
      
    
    <div class="confluence-information-macro confluence-information-macro-note">
    
    <span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>
    
    <div class="confluence-information-macro-body">
    
    **Note:** On Linux systems, you might need to append `sudo` to your
    `npm` commands so that you can issue the install and uninstall
    commands. For more information, see [Known
    Issues](Release-Notes_417294291.html#ReleaseNotes-knownIssues).
    
    </div>
    
    </div>
    
    Brightside CLI is installed on your PC.

4.  <span>You must create a Brightside CLI profile before you can issue
    Brightside CLI commands that communicate with z/OSMF on mainframe
    systems. </span><span>For more information about the available
    commands and options for creating z/OSMF profiles, issue the `bright
    help explain profiles` and  </span>`bright zosmf create
    bright-profile --help`<span>
     </span><span>commands.</span>
    
    <div class="confluence-information-macro confluence-information-macro-tip">
    
    <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"></span>
    
    <div class="confluence-information-macro-body">
    
    **Tip:** Brightside profiles contain information (for example, host
    name, port, and user ID) that is required for Brightside to interact
    with remote systems. Profiles allow you to "target" a system,
    region, or instance for a command. You create and configure profiles
    at the command group level. Most command groups require a "zosmf"
    Brightside profile.
    
    </div>
    
    </div>

5.  <span>To ensure that your Brightside CLI profile can communicate
    with z/OSMF on mainframe systems, issue the following z/OSMF profile
    validation command:</span>
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    bright zosmf validate profile
    ```
    
    </div>
    
    </div>
    
    The command runs a series of tests and returns a report. If the
    report returns any failures or warnings, send the report to your
    systems programmer for analysis. Failures might indicate that your
    Brightside CLI profile is not configured correctly for your
    environment. For more information about how to use command,
    see [Validate Installation](Validate-Installation_430335233.html).

After you install and configure Brightside CLI, issue the `bright
--help` command to view a list of available commands. For more
information, see [How to Display Brightside CLI
Help](How-to-Display-Brightside-CLI-Help_429365003.html).

## Update Brightside CLI

Brightside CLI will have periodic updates. You can identify your current
version and apply updates through the command line.

**Follow these steps:**

1.  Download an updated Brightside CLI installation package from the
    **Downloads** section
    on [validate.ca.com](https://validate.ca.com/project/version/item.html?cap=13283cc32fd9439c85aeb18bba4ac1f6&arttypeid=%7B4109d6e9-6c06-448b-8eb2-6601a5616391%7D&artid=%7B5ACC31C0-2176-437F-B06B-8C572D48C76C%7D).

2.  Open a command line window. Browse to the directory that contains
    the new Brightside CLI installation package. Issue the following
    command to update Brightside CLI:
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
     npm install -g <file_name>
    ```
    
    </div>
    
    </div>

3.  To confirm that the update was successful, issue the following
    command to display the version of Brightside CLI that is installed
    on your computer:
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    bright -V
    ```
    
    </div>
    
    </div>

## Uninstall Brightside CLI

To uninstall Brightside CLI, issue the following command:

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
npm uninstall -g
```

</div>

</div>

If you don't receive any errors, the uninstall process was successful.

</div>

</div>

</div>

</div>

  - <span id="n-417294290">[Brightside CLI](index.html)</span>
      - <span id="n-417294291">[Release
        Notes](Release-Notes_417294291.html)</span>
    <!-- end list -->
      - <span id="n-429364995">[Installing](Installing_429364995.html)</span>
          - <span id="n-433363261">[Overview of the z/OS Management
            Facility Configuration Process](433363261.html)</span>
              - <span id="n-433363262">[Configure z/OS Management
                Facility](433363262.html)</span>
            <!-- end list -->
              - <span id="n-433363263">[Configure z/OS Management
                Facility Security](433363263.html)</span>
            <!-- end list -->
              - <span id="n-433363264">[Configure z/OS Management
                Facility Cloud Provisioning](433363264.html)</span>
            <!-- end list -->
              - <span id="n-433363265">[Configure z/OS Management
                Facility Cloud Provisioning
                Security](433363265.html)</span>
        <!-- end list -->
          - <span id="n-429364999">[Install Brightside
            CLI](Install-Brightside-CLI_429364999.html)</span>
        <!-- end list -->
          - <span id="n-430335233">[Validate
            Installation](Validate-Installation_430335233.html)</span>
              - <span id="n-433363269">[Identify and Correct Problems
                Detected by the Validate Profile
                Command](Identify-and-Correct-Problems-Detected-by-the-Validate-Profile-Command_433363269.html)</span>
    <!-- end list -->
      - <span id="n-429365002">[Using](Using_429365002.html)</span>
          - <span id="n-429365003">[How to Display Brightside CLI
            Help](How-to-Display-Brightside-CLI-Help_429365003.html)</span>
        <!-- end list -->
          - <span id="n-447395688">[Brightside CLI Command
            Groups](Brightside-CLI-Command-Groups_447395688.html)</span>
        <!-- end list -->
          - <span id="n-433363274">[Enable and Disable Experimental
            Commands](Enable-and-Disable-Experimental-Commands_433363274.html)</span>
        <!-- end list -->
          - <span id="n-441193419">[Brightside CLI
            Scenarios](Brightside-CLI-Scenarios_441193419.html)</span>
              - <span id="n-441193420">[Submit a Job and Print Job
                Output](Submit-a-Job-and-Print-Job-Output_441193420.html)</span>
    <!-- end list -->
      - <span id="n-38207496">[Legal
        Notices](Legal-Notices_38207496.html)</span>

<div id="footer">

<div class="section footer-body">

Copyright © 2018 CA. All rights reserved.

<div class="footer-logo">

</div>

Document generated on Mar 01, 2018 17:24.

</div>

</div>

</div>
