# Installing Zoe Brightside

As a systems programmer or application developer, you install Zoe Brightside on your PC.

Before you install Zoe Brightside, ensure that you meet the [Prerequisites](cli-precli.md).

**Note:** You might encounter problems when you attempt to install
Zoe Brightside depending on your operating system and
environment. For more information and workarounds, see [Troubleshooting Installing Zoe Brightside](cli-troubleshootinginstallingcli.md).

  - [Install Zoe Brightside from package](#install-zoe-brightside-from-package)
  - [Alternative method to install Zoe Brightside](#alternative-method-to-install-zoe-brightside)
  - [Update Zoe Brightside](#update-zoe-brightside)

## Install Zoe Brightside from package

Install CA Brightside on PCs that are running a Windows, Linux, or macOS operating system.

**Follow these steps:**

1.  [Address the prerequisites](cli-precli.md).

2. [Obtain the Project Zoe installation media](installing.md), which includes the brightside.tgz file. Use FTP to distribute the brightside.tgz file to client workstations.
    Users can now install Zoe Brightside on their PC.

3.  Open a command line window. For example, Windows Command Prompt. Browse to the directory where you downloaded the Zoe Brightside installation package (.tgz file). Issue the following command to install Brightside CLI on your PC:
    
    ```
    npm install -g <file_name>
    ```
    
    **Note:** On Linux systems, you might need to append `sudo` to your
    `npm` commands so that you can issue the install and uninstall
    commands. For more information, see [Troubleshooting Installing Zoe Brightside](cli-troubleshootinginstallingcli.md).
    
    Brightside CLI is installed on your PC.

4.  Create a `zosmf` profile so that you can issue commands that communicate with z/OSMF.
    
    **Note:** For information about how to create a profile, see [Create a profile](cli-createaprofile.md).
    
    **Tip:** Zoe Brightside profiles contain information that is required
    for the product to interact with remote systems. For example, host
    name, port, and user ID. Profiles let you target unique systems,
    regions, or instances for a command. Most CA Brightside [command
    groups](cli-commandgroups.md) require a Zoe Brightside
    `zosmf` profile.

After you install and configure CA Brightside, you can issue the `bright --help` command to view a list of available commands. For moreinformation, see [Display Help](cli-howtodisplaybrightsidehelp.md).


## Alternative method to install Zoe Brightside
If your PC is connected to the internet, you can use the following method to install Zoe Brightside from an npm registry.

**Follow these steps:**

1.  Issue the following command to set the registry to the Zoe Brightside scoped package on Bintray:

    ```
    npm config set @brightside:registry https://api.bintray.com/npm/ca/brightside
    ```

2.  Issue the following command to install Zoe Brightside from the registry:
    
    ```
    npm install -g @brightside/core@latest
    ```
    
    Zoe Brightside is installed on your PC.

3.  Create a `zosmf` profile so that you can issue commands that communicate with z/OSMF.
    
    **Note:** For information about how to create a profile, see [Create
    a
    Profile](cli-createaprofile.md).
    
    
    **Tip:** Zoe Brightside profiles contain information that is required
    for the product to interact with remote systems. For example, host
    name, port, and user ID. Profiles let you target unique systems,
    regions, or instances for a command. Most CA Brightside [command
    groups](cli-commandgroups.md) require a Zoe Brightside
    `zosmf` profile.
    

After you install and configure CA Brightside, you can issue the `bright
--help` command to view a list of available commands. For more information, see [Display Help](cli-howtodisplaybrightsidehelp.md).

  - [Uninstall Zoe Brightside](cli-uninstallcli.md)

