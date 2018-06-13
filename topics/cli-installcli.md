# Installing Zoe Brightside
As a systems programmer or application developer, you install Brightside CLI on your PC. 

Before you install Zoe Brightside, ensure that you meet the [Prerequisites](cli-precli.md).

**Note:** You might encounter problems when you attempt to install
Zoe Brightside depending on your operating system and
environment. For more information and workarounds, see [Troubleshooting Installing Zoe Brightside](cli-troubleshootinginstallingcli.md).

## Install Zoe Brightside

To use Zoe Brightside on your PC, install the product from that is available at your site. 

**Follow these steps:**

1. [Obtain the Project Zoe installation media](installing.md), which includes the brightside.tgz file. Use FTP to distribute the brightside.tgz file to client workstations.
    Users can now install Zoe Brightside on their PC.

4.  Open a command line window. Browse to the directory where you
    downloaded the Brightside CLI installation package (.tgz file). Issue the
    following command to install Brightside CLI on your PC:
    
    ```
    npm install -g <file_name>
    ```
    
    **Note:** On Linux systems, you might need to append `sudo` to your
    `npm` commands so that you can issue the install and uninstall
    commands. For more information, see [Troubleshooting Installing Zoe Brightside](cli-troubleshootinginstallingcli.md).
    
    Brightside CLI is installed on your PC.

5.  You must create a Brightside CLI profile before you can issue
    Brightside CLI commands that communicate with z/OSMF on mainframe
    systems. For more information about the available
    commands and options for creating z/OSMF profiles, issue the `bright help explain profiles` and  `bright zosmf create bright-profile --help` commands.
    
    **Tip:** Brightside profiles contain information (for example, host
    name, port, and user ID) that is required for Brightside to interact
    with remote systems. Profiles allow you to "target" a system,
    region, or instance for a command. You create and configure profiles
    at the command group level. Most command groups require a "zosmf"
    Brightside profile.    

6.  To ensure that your Brightside CLI profile can communicate
    with z/OSMF on mainframe systems, issue the following z/OSMF profile
    validation command:    
   
    ```
    bright zosmf validate profile
    ```
        
    The command runs a series of tests and returns a report. If the
    report returns any failures or warnings, send the report to your
    systems programmer for analysis. Failures might indicate that your
    Brightside CLI profile is not configured correctly for your
    environment. For more information about how to use command,
    see [Validating Installation](cli-validateInstallation.md).

After you install and configure Brightside CLI, issue the `bright --help` command to view a list of available commands. For more
information, see [How to Display Zoe Brightside Help](cli-howtodisplaybrightsidehelp.md).
