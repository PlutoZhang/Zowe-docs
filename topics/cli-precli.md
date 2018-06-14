# System requirements for Zoe Brightside
Review and meet the following prerequisites before you install and
use Zoe Brightside:

  - [Supported platforms](#supported-platforms)
  - [Free disk space](#free-disk-space)
  - [Prerequisite software](#prerequisite-software)

## Supported platforms

You can use Zoe Brightside with the following platforms:

  - **Local workstations:**    
  You can install Zoe Brightside on any Windows or Linux operating system. For more information about known
    issues and workarounds, see [Troubleshooting installing Zoe Brightside](cli-troubleshootinginstallingcli.nd).

  - **Mainframe systems:**   
    Zoe Brightside was designed and tested to integrate with IBM z/OS Management Facility (z/OSMF) running on IBM z/OS version 2.2 or higher.

    **Important\!** Before you can use Zoe Brightside to interact with the mainframe, systems programmers must install and configure IBM z/OSMF in your environment. The IBM z/OS Management Facility guide on the IBM Knowledge Center is the primary source of information about how systems programmers can install and configure z/OSMF. We provide supplemental information about Zoe Brightside-specific tips or requirements to which systems programmers can refer. For more
    information, see [Prerequisites for z/OSMF configuration](prezosmf.md).

## Free disk space

Zoe Brightside requires approximately **100 MB** of free disk space. The actual quantity of free disk space consumed might vary
depending on the operating system on which you install Zoe Brightside.

## Prerequisite software
The following software is required before you can install and use the product on your PC: 

**Note:** We do not maintain the prerequisite software that Zoe Brightside requires. You are responsible for updating Node.js and other prerequisites on your PC. We recommend that you update Node.js regularly to the latest Long Term Support (LTS) version.

### Windows operating systems
Windows operating systems require the following software:

- **Node.js v8.0 or higher:**   
  Click here to [Download Node.js](https://nodejs.org/en/download/)       
  
  **Note:** Npm is included with the Node.js installation.

- **Node Package Manager (npm) v5.0 or higher**

- **Python v2.7**   
  See the C++ Compiler prerequisite. The command that installs C++ Compiler also installs Python on Windows.

- **C++ Compiler**  
  From an administrator command prompt, issue the following command:  
  ``npm install --global --production --add-python-to-path windows-build-tools``

### Mac operating systems
 Mac operating systems require the following software:

- **Node.js v8.0 or higher:**   
  Click here to [Download Node.js](https://nodejs.org/en/download/)   
  **Note:** Npm is included with the Node.js installation.

- **Node Package Manager (npm) v5.0 or higher**   
  
  **Tip:** If you are installing Node.js a macOS operating system, we recommend that you install `nodejs` and `nodejs-legacy` using the instructions on the Nodejs website (using package manager). For example, you can install `nodejs-legacy` using the command `sudo apt install nodejs-legacy`. With `nodejs-legacy`, you can issue node commands rather than typing `nodejs`.

- **Python v2.7**  
  Click here to [Download Python 2.7](https://www.python.org/download/releases/2.7/)

- **C ++ Compiler**  
  The gcc compiler is included with MacOS. To confirm that you have the compiler, enter the command `gcc –help`. If you do not have the compiler installed, you can acquire gcc through a Google search.

### Linux operating systems
Linux  operating systems require the following software:

- **Node.js v8.0 or higher:**   
  Click here to [Download Node.js](https://nodejs.org/en/download/)   
  **Note:** Npm is included with the Node.js installation.

- **Node Package Manager (npm) v5.0 or higher**   
  **Tip:** If you are installing Node.js a Linux operating system, we recommend that you install `nodejs` and `nodejs-legacy` using the instructions on the Nodejs website (using package manager). For example, you can install `nodejs-legacy` using the command `sudo apt install nodejs-legacy`. With `nodejs-legacy`, you can issue node commands rather than typing `nodejs`.

- **Python v2.7**  
  Included w/ most Linux distributions

- **C ++ Compiler**  
  Gcc is included with most Linux distributions. To confirm that gcc is installed, enter the command `gcc –version`. If gcc is not installed, you can enter one of the following commands:

  - **Red Hat**  
    `sudo yum install gcc`
  - **Debian/Ubuntu**  
    `sudo apt-get update`  
    `sudo apt-get install build-essential`
  - **Arch Linux**  
    `sudo pacman -S gcc`

- **Libsecret**  
  Enter one of the following commands:
  - **Red Hat**  
    `sudo yum install libsecret-devel`
  - **Debian/Ubuntu**  
    `sudo apt-get install libsecret-1-dev`
  - **Arch Linux**  
    `sudo pacman -S libsecret`

- **Make**  
  Make is included with most Linux distributions. To confirm that Make is installed, enter the command `make –-version`. If Make is not installed, you can enter one of the following commands:

  - **Red Hat**  
    `sudo yum install devtoolset-7`
  - **Debian/Ubuntu**  
    `sudo apt-get install build-essential`
  - **Arch Linux**  
    `sudo pacman -S base-devel`

**More information:**

  - [Product overview](cli-releasenotes.md)
  - [Installing Zoe Brightside](cli-installcli.md)
  - [Creating a profile](cli-createaprofile.md)
  - [Testing connection to z/OSMF](cli-validateInstallation.md)
