# Installing Brightside CLI
As a systems programmer or application developer, you install Brightside
CLI on your PC. You can install Brightside CLI on any
PC that is running a Windows, Linux, macOS operating
system that supports Node.js version 6 or
later. 

Before you install Brightside CLI, ensure that you meet the [Prerequisites](precli.md).

**Note:** You might encounter problems when you attempt to install
Brightside CLI depending on your operating system and
environment. For more information and workarounds, see [Troubleshooting Installing Brightside CLI](cli-troubleshootinginstallingcli.md).

## Install Brightside CLI

To use Brightside CLI on your PC, install the product from that is available at your site. 

**Follow these steps:**

1. [Obtain the Project Giza installation media](installing.md), which includes the brightside.tgz file. Use FTP to distribute the brightside.tgz file to client workstations. Users can now install Brightside CLI on their PC.

2.  Open a command line window. Browse to the directory where you
    downloaded the Brightside CLI installation package (.tgz file). Issue the following command to install Brightside CLI on your PC:
    
    ```
    npm install -g <file_name>
    ```
    
    **Note:** On Linux systems, you might need to append `sudo` to your `npm` commands so that you can issue the install and uninstall commands. For more information, see [Troubleshooting Installing Brightside CLI](cli-troubleshootinginstallingcli.md).

3.  You must create a Brightside CLI profile before you can issue
    Brightside CLI commands that communicate with z/OSMF. For more information about the available commands and options for creating z/OSMF profiles, issue the following commands:
    
    ```
    bright help explain profiles
    ```
    ```
    bright zosmf create bright-profile --help
    ```
    
    **Tip:** Brightside CLI profiles contain information (for example, host name, port, and user ID) that is required for Brightside to interact with remote systems. Profiles let you "target" a system, region, or instance for a command. You create and configure profiles at the command group level. Most command groups require a "zosmf" Brightside profile.    

4.  To ensure that your Brightside CLI profile can communicate
    with z/OSMF on mainframe systems, issue the following z/OSMF profile validation command:    
   
    ```
    bright zosmf validate profile
    ```
        
    The command runs a series of tests and returns a report. When the report returns failures or warnings, send the report to your systems programmer for analysis. Failures might indicate that your Brightside CLI profile is not configured correctly for your environment. For more information about how to use command, see [Validating Installation](cli-validateInstallation.md).

After you install and configure Brightside CLI, issue the `bright --help` command to view a list of available commands. For more information, see [How to Display Brightside CLI Help](cli-howtodisplaybrightsidehelp.md).
