# Testing connection to z/OSMF
After you configure a Zoe Brightside `zosmf` profile to connect to z/OSMF on your mainframe systems, you can issue a command at any time to receive diagnostic information from the server and confirm that your profile can communicate with z/OSMF.

**Tip:** In this documentation we provide command syntax to help you create a basic profile. We recommend that you append `--help` to the end of commands in the product to see the complete set of commands and options available to you. For example, issue `bright profiles --help` to learn more about how to list profiles, switch your default profile, or create different profile types.

After you create a profile, run a test to verify that Zoe Brightside can communicate properly with z/OSMF. You can test your default profile and any other Zoe Brightside profile that you created.

**Default profile**

  - Verify that you can use your default profile to communicate with z/OSMF by issuing the following command:

    ```
    bright zosmf check status
    ```

**Specific profile**

  - Verify that you can use a specific profile to communicate with
    z/OSMF by issuing the following command: 

    ```
    bright zosmf check status --zosmf-profile <profile_name>
    ```

The commands return a success or failure message and display information about your z/OSMF server. For example, the z/OSMF version number and a list of installed plug-ins. Report any failure to your systems administrator and use the information for diagnostic purposes.

**More information:**

  - [Creating a Zoe Brightside profile](cli-createaprofile.md)
