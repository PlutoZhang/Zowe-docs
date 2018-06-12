# Uninstall Zoe Brightside
You can uninstall Zoe Brightside when you no longer want to use the product.

**Important\!** The uninstall process does not delete the  profiles and credentials that you created when using the product from your PC. To delete the profiles from your PC, delete them before you uninstall Zoe Brightside.

The following steps describe how to list the profiles that you created, delete the profiles, and uninstall Zoe Brightside.

**Follow these steps:**

1.  Open a command line window. 
    
    **Note:** If you do not want to delete the Zoe Brightside profiles from your PC, go to Step 5.
    
2.  List all profiles that you created for a [Command Group](commandgroups.md) by issuing the following command:
  
    ```
    ca-code-default bright profiles list <profileType>
    ```
    **Example:**
    
    ``` ca-code-default
    $ bright profiles list zosmf
    The following profiles were found for the module zosmf:
    'SMITH-123' (DEFAULT)
    smith-123@SMITH-123-W7 C:\Users\SMITH-123
    $
    ```
3.  Delete all of the profiles that are listed for the command group by issuing the following command: 
    
    **Tip:** For this command, use the results of the `list`
    command.    
    **Note:** When you issue the `delete` command, it deletes the
    specified profile and its credentials from the credential vault in your PC's operating system.
    
    ``` ca-code-default
    bright profiles delete <profileType> <profileName> --force  
    ```
        **Example:**
    
    ``` ca-code-default
    bright profiles delete zosmf SMITH-123 --force
    ```
  
4.  Repeat Steps 2 and 3 for all Zoe Brightside command groups and
    profiles.

5.  Uninstall Zoe Brightside by issuing the following command:
    
    ``` ca-code-default
    npm uninstall --global @brightside/core
    ```
    The uninstall process removes all Zoe Brightside installation
    directories and files from your PC.

6.  Delete the following directory on your PC. The directory contains the Zoe Brightside log files and other miscellaneous files that were generated when you used the product.
    

    **Tip:** Deleting the `C:\Users\<user_name>\.brightside`  directory does not harm your PC.
    
7.  Issue the following command to clear your scoped npm registry:
    
    ``` ca-code-default
    npm config set @brightside:registry
    ```
    
**More Information:**

  - [Install Zoe Brightside](cli-installcli.md)
