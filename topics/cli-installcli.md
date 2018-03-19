# Installing Brightside CLI
As a systems programmer or application developer, you install Brightside
CLI on your personal computer. You can install Brightside CLI on any
personal computer that is running a Windows, Linux, macOS operating
system that supports Node.js version 6 or
later.

**Important!** Before you can use Brightside CLI to interact with the
mainframe, a systems programmer must install and configure IBM z/OSMF in
your environment. For more information about how systems programmers and
security administrators perform the z/OSMF configuration, see [Overview of the z/OS Management Facility Configuration Process](cli-overviewzosmfconfig.md).

Node.js® is a JavaScript runtime environment on which we
architected Brightside CLI. You use the Node.js package manager (npm)
to install Brightside CLI. After you install Node.js, you can then
install Brightside CLI using the Node.js package
manager. 

**Note:** CA Technologies does not maintain the prerequisite
software that Brightside CLI requires. You are responsible
for updating Node.js and other prerequisites on your PC. We recommend
that you update Node.js regularly to the latest Long Term Support (LTS)
version.

**Important!** You might encounter problems when you attempt to install
Brightside CLI depending on your operating system and
environment. For more information and workarounds, see [Troubleshooting Installing Brightside CLI](cli-troubleshootinginstallingcli.md).

**Follow these steps:**

1.  Go to the *Installing Node.js via package manager* website at
    the following URL, and follow the instructions for installing
    Node.js on your operating
    system:
    
    ```https://nodejs.org/en/download/package-manager```

    **Tip:** If you are installing Node.js on a Linux or a macOS
    operating system, CA recommends that you install `nodejs` and
    `nodejs-legacy` using the instructions on the Nodejs website (using
    package manager). For example, you can install nodejs-legacy using
    the command `sudo apt install nodejs-legacy`. With `nodejs-legacy`,
    you can issue `node` commands rather than typing
    `nodejs`.
    
    Node.js is installed on your PC.

2.  Download the Brightside CLI installation package from the
    **Downloads** section on [validate.ca.com.](https://validate.ca.com/project/version/item.html?cap=13283cc32fd9439c85aeb18bba4ac1f6&arttypeid=%7B4109d6e9-6c06-448b-8eb2-6601a5616391%7D&artid=%7B5ACC31C0-2176-437F-B06B-8C572D48C76C%7D)

3.  Open a command line window. Browse to the directory where you
    downloaded the Brightside CLI installation package. Issue the
    following command to install Brightside
    CLI:
    
    ```npm install -g <file_name>```
    
    **Note:** On Linux systems, you might need to append `sudo` to your
    `npm` commands so that you can issue the install and uninstall
    commands. For more information, see [Troubleshooting Installing Brightside CLI](cli-troubleshootinginstallingcli.md).
    
    Brightside CLI is installed on your PC.

4.  You must create a Brightside CLI profile before you can issue
    Brightside CLI commands that communicate with z/OSMF on mainframe
    systems. For more information about the available
    commands and options for creating z/OSMF profiles, issue the `bright help explain profiles` and  `bright zosmf create bright-profile --help` commands.
    
    **Tip:** Brightside profiles contain information (for example, host
    name, port, and user ID) that is required for Brightside to interact
    with remote systems. Profiles allow you to "target" a system,
    region, or instance for a command. You create and configure profiles
    at the command group level. Most command groups require a "zosmf"
    Brightside profile.    

5.  <span>To ensure that your Brightside CLI profile can communicate
    with z/OSMF on mainframe systems, issue the following z/OSMF profile
    validation command:    
   
    ```bright zosmf validate profile```
        
    The command runs a series of tests and returns a report. If the
    report returns any failures or warnings, send the report to your
    systems programmer for analysis. Failures might indicate that your
    Brightside CLI profile is not configured correctly for your
    environment. For more information about how to use command,
    see [Validating Installation](cli-validateInstallation.md).

After you install and configure Brightside CLI, issue the `bright --help` command to view a list of available commands. For more
information, see [How to Display Brightside CLI Help](cli-howtodisplaybrightsidehelp.md).
