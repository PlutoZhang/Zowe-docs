# Installing Zoe Brightside

As a systems programmer or application developer, you install Zoe Brightside on your PC. You can use either of the following methods to install Zoe Brightside.

## Install Zoe Brightside from local package

Install Zoe Brightside on PCs that are running a Windows, Linux, or macOS operating system.

**Follow these steps:**

1. [Address the prerequisites](../planinstall/cli-precli.md).
2. [Obtain the Project Zoe installation files](../zoegettingstarted.md), which includes the brightside-bundle.zip file. Use FTP to distribute the brightside-bundle.zip file to client workstations.
3. Open a command line window. For example, Windows Command Prompt. Browse to the directory where you downloaded the Zoe Brightside installation bundle \(.zip file\). Issue the following command to unzip the files:

   ```text
   unzip brightside-bundle.zip
   ```

   The command expands four TGZ packages into your working directory - Zoe Brightside, one plug-in, and the odbc\_cli folder.

4. Issue the following command to install Zoe Brightside on your PC:

   ```text
    npm install -g brightside-core-1.0.1.tgz
   ```

   **Note:** On Linux systems, you might need to append `sudo` to your `npm` commands so that you can issue the install and uninstall commands. For more information, see [Troubleshooting Installing Zoe Brightside](cli-troubleshootinginstallingcli.md).

   Zoe Brightside is installed on your PC. See [Installing Plug-ins](../../zoe_extending/cli-extending/cli-installplugins.md) for information about the commands for installing plug-ins from the package.

5. Create a `zosmf` profile so that you can issue commands that communicate with z/OSMF.

   **Note:** For information about how to create a profile, see [Creating a Zoe Brightside profile](cli-createaprofile.md).

   **Tip:** Zoe Brightside profiles contain information that is required for the product to interact with remote systems. For example, host name, port, and user ID. Profiles let you target unique systems, regions, or instances for a command. Most Zoe Brightside [command groups](../../using/cli-usingcli/cli-commandgroups.md) require a Zoe Brightside `zosmf` profile.

After you install and configure Zoe Brightside, you can issue the `bright --help` command to view a list of available commands. For moreinformation, see [Display Help](../../using/cli-usingcli/cli-howtodisplaybrightsidehelp.md).

## Install Zoe Brightside from Bintray registry

If your PC is connected to the Internet, you can use the following method to install Zoe Brightside from an npm registry.

**Follow these steps:**

1. Issue the following command to set the registry to the Zoe Brightside scoped package on Bintray. In addition to setting the scoped registry, your non-scoped registry must be set to an npm registry that includes all of the dependencies for Zoe Brightside, such as the global npm registry:

   ```text
   npm config set @brightside:registry https://api.bintray.com/npm/ca/brightside
   ```

2. Issue the following command to install Zoe Brightside from the registry:

   ```text
   npm install -g @brightside/core@latest
   ```

   Zoe Brightside is installed on your PC. For information about plug-ins for Zoe Brightside, see [Extending Zoe Brightside](../../zoe_extending/cli-extending/).

3. Create a `zosmf` profile so that you can issue commands that communicate with z/OSMF. For information about how to create a profile, see [Creating a Zoe Brightside profile](cli-createaprofile.md).

   **Tip:** Zoe Brightside profiles contain information that is required for the product to interact with remote systems. For example, host name, port, and user ID. Profiles let you target unique systems, regions, or instances for a command. Most Zoe Brightside [command groups](../../using/cli-usingcli/cli-commandgroups.md) require a Zoe Brightside `zosmf` profile.

After you install and configure Zoe Brightside, you can issue the `bright --help` command to view a list of available commands. For more information, see [How to display Zoe Brightside help](../../using/cli-usingcli/cli-howtodisplaybrightsidehelp.md).

**Note:** You might encounter problems when you attempt to install Zoe Brightside depending on your operating system and environment. For more information and workarounds, see [Troubleshooting Installing Zoe Brightside](cli-troubleshootinginstallingcli.md).

**More information:**

* [Uninstalling Zoe Brightside](../uninstall/cli-uninstallcli.md)

