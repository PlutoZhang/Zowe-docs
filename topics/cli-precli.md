# CA Brightside Community Edition : Prerequisites

</div>

<div id="content" class="view">

<div class="page-metadata">

</div>

<div id="main-content" class="wiki-content group">

Review and meet the following prerequisites before you install and
use CA Brightside:

<div class="toc-macro rbtoc1528725935675">

  - [Supported Platforms](#Prerequisites-SupportedPlatforms)
  - [Free Disk Space](#Prerequisites-FreeDiskSpace)
  - [Prerequisite Software](#Prerequisites-PrerequisiteSoftware)

</div>

## Supported Platforms

You can use CA Brightside with the following platforms:

  - **Local Workstations:** You can install CA Brightside on any Windows
    or Linux operating system. <span>For more information about known
    issues and workarounds, see </span>[Known
    Issues.](Release-Notes_473021281.html#ReleaseNotes-knownIssues)

  - **Mainframe Systems:** CA Brightside was designed and tested to
    integrate with IBM z/OS Management Facility (z/OSMF) running on IBM
    z/OS version 2.2 or
    higher.
       
    **Important\!** Before you can use CA Brightside to interact with
    the mainframe, systems programmers must install and configure IBM
    z/OSMF in your environment. The IBM z/OS Management Facility guide
    on the IBM Knowledge Center is the primary source of information
    about how systems programmers can install and configure z/OSMF. We
    provide supplemental information about CA Brightside-specific tips
    or requirements to which systems programmers can refer. For more
    information, see [z/OSMF Configuration Overview](473021286.html).
    
    </div>
    
    </div>

## Free Disk Space

CA Brightside requires approximately <span>100 MB</span> of free disk
space. The actual quantity of free disk space consumed might vary
depending on the operating system on which you install CA Brightside.

## Prerequisite Software

The following software is required before you can install and use the
product on your
PC: 

**Note:** CA Technologies does not maintain the prerequisite software
that CA Brightside requires. You are responsible for updating Node.js
and other prerequisites on your PC. We recommend that you update Node.js
regularly to the latest Long Term Support (LTS) version.

### Windows

### Mac

### Linux

**Node.js v8.0 or higher**

**Node Package Manager (npm) v5.0 or higher**

<div class="content-wrapper">

[Download Node.js](https://nodejs.org/en/download/)

Npm is included with the Node.js
installation

<div class="confluence-information-macro confluence-information-macro-tip">

<span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Tip:** If you are installing Node.js on a Linux or a macOS operating
system, we recommend that you install `nodejs` and `nodejs-legacy` using
the instructions on the Nodejs website (using package manager). For
example, you can install `nodejs-legacy` using the command `sudo apt
install nodejs-legacy`. With `nodejs-legacy`, you can issue `node`
commands rather than typing
`nodejs`.<span style="color: rgb(255,0,0);"> </span>

</div>

</div>

</div>

**Python v2.7**

See the C++ Compiler prerequisite in this table. The command that
installs C++ Compiler also installs Python on Windows.

[Download
Python 2.7](https://www.python.org/download/releases/2.7/)[<span> </span>](https://www.python.org/download/releases/2.7/)

Included w/ most Linux distributions

**C++ Compiler**

`npm install --global --production windows-build-tools`

The gcc compiler is included with MacOS. To confirm that you have the
compiler, enter the command `gcc –help`. If you do not have the compiler
installed, you can aquire gcc through a Google search.

Gcc is included with most Linux distributions. To confirm that gcc is
installed, enter the command `gcc –version`. If gcc is not installed,
you can enter one of the following commands:

  - **Red Hat**  
    sudo yum install gcc
  - **Debian/Ubuntu**:  
    sudo apt-get update  
    sudo apt-get install build-essential
  - **Arch Linux**  
    sudo pacman -S gcc

**Libsecret**

Not required

Not required. Mac uses the OSX Keychain to store sensitive information.

<span>Enter one of the following commands:</span>

  - **Red Hat**  
    sudo yum install libsecret-devel
  - **Debian/Ubuntu**  
    sudo apt-get install libsecret-1-dev
  - **Arch Linux**  
    sudo pacman -S
libsecret

<div class="confluence-information-macro confluence-information-macro-information">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**More Information:**

  - [Release Notes](Release-Notes_473021281.html)
  - [Install CA Brightside](Install-CA-Brightside_473021289.html)
  - [Create a Profile](Create-a-Profile_473021290.html)
  - [Test Connection to z/OSMF](473021291.html)

