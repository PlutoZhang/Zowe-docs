# Troubleshooting installing Zoe Brightside
The following topics contain information that can help you troubleshoot problems when you encounter unexpected behavior using Zoe Brightside.

## `npm install -g `Command Fails Due to an EPERM Error

**Valid on Windows**

**Symptom:**

This behavior is due to a problem with Node Package Manager (npm). There
is an open issue on the npm GitHub repository to fix the defect.

**Solution:**

If you encounter this problem, some users report that repeatedly
attempting to install Zoe Brightside yields success. Some users also
report success using the following workarounds:

  - Issue the `npm cache clean` command.

  - Uninstall and reinstall Zoe Brightside. For more information,
    see [Install Zoe Brightside](cli-installcli.md).

  - `Add the --no-optional` flag to the end of the `npm install` command.

## `Sudo` syntax required to complete some installations

**Valid on Linux**

**Symptom:** 

The installation fails on Linux. 

**Solution:**

Depending on how you configured Node.js on Linux or Mac, you might need
to add the prefix `sudo `before the `npm install -g` command or the `npm
uninstall -g` command. This step gives Node.js write access to the
installation directory.

## `sudo npm install -g` command fails with an `EPERM` error 

**Valid on Linux**

**Symptom:**

You receive an `EPERM` error after appending `sudo` to the install
command.

**Solution:**

You can run a script on your Linux PC to resolve the problem. The script
performs the following actions:

1.  Verifies that the Zoe Brightside prerequisites are installed.
2.  Prompts you to specify a directory location to which to install
    global node modules.
3.  Creates the specified directory.
4.  Sets the npm global install directory to the new directory.
5.  Adds the new directory to the $PATH environmental variable.  
    You can install Zoe Brightside.

**Follow these steps:**

1.  Download the file named `setup-node.sh` from the [Downloads](https://github.com/gizafoundation/Downloads/releases) repo.

2.  Issue the following command to add executable permissions for all
    users on the` setup-node.sh` shell script:
        
    ```
    chmod +x setup-node.sh
    ```
    
3.  Execute the shell script.

4.  Follow the prompts to enter a new directory location for global node
    modules. If the script runs successfully, you can install Zoe Brightside  on your PC. See [Install Zoe Brightside](cli-installcli.md) for more
    information. 

**Tip:** If the script fails, rerun the script. If the script fails again on the same step, you can perform the script operations manually. See the npm documentation about [how to change the default global node module directory](https://docs.npmjs.com/getting-started/fixing-npm-permissions#option-two-change-npms-default-directory)
manually.

## `npm install -g` command fails due to `npm ERR! Cannot read property 'pause' of undefined` error

**Valid on Windows or Linux**

**Symptom:**

You receive the error message `npm ERR! Cannot read property 'pause' of undefined` when you attempt to install the product. 

**Solution:**

This behavior is due to a problem with Node Package Manager (npm). If
you encounter this problem, revert to a previous version of npm that
does not contain this defect. To revert to a previous version of npm,
issue the following command:

`npm install npm@5.3.0 -g`

## Node.js commands do not respond as expected

**Valid on Windows or Linux**

**Symptom:**

You attempt to issue node.js commands and you do not receive the expected  output.

**Solution:**

There might be a program that is named *node* on your path. The Node.js installer automatically adds a program that is named *node* to your path. When there are pre-existing programs that are named *node* on your computer, the program that appears first in the path is used. To correct this behavior, change the order of the programs in the path so that Node.js appears first.


## Installation Fails on Oracle Linux 6

**Valid on Oracle Linux 6**

**Symptom:**

You receive error messages when you attempt to install the product on an
Oracle Linux 6 operating system. 

**Solution:**

Install the product on Oracle Linux 7 or another Linux or Windows OS. Zoe Brightside is not compatible with Oracle Linux 6.

