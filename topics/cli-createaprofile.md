# Creating a Zoe Brightside profile
Profiles are a Zoe Brightside function that lets you store configuration information for use on multiple commands. You can create a profile that contains your username, password, and connection details for a particular mainframe system, then reuse that profile to avoid typing it again on every command. You can switch between profiles to quickly target different mainframe
subsystems.

**Important\!** A `zosmf` profile is required to issue most Zoe Brightside commands. The first profile that you create becomes your default profile. When you issue any command that requires
a `zosmf` profile, the command executes using your default profile
unless you specify a specific profile name on that command.

**Follow these steps:**

1.  To create a `zosmf` profile, issue the following command.  
  Refer to the available options in the help text to define your profile:   
    ```
    bright profiles create zosmf-profile --help
    ```

**Note:** After you create a profile, verify that it can communicate with z/OSMF. For more information, see [Test Connection to z/OSMF](cli-validateInstallation.md).
