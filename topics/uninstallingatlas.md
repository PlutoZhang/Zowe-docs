# Uninstalling Atlas

To uninstall Atlas, take the following steps:
2.  Stop your Atlas Liberty server by running the following operator command:

    ```
    P FEKATLS
    ```

3.  Delete the FEKATLS member from your system PROCLIB data set.
4.  Remove RACF® \(or equivalent\) definitions with the following command:

    ```
    RDELETE STARTED (FEKATLS.*)
    SETR RACLIST(STARTED) REFRESH
    REMOVE (userid) GROUP(IZUUSER)
    ```

5.  Delete the z/OS® UNIX™ System Services Atlas directory and files from the Atlas installation directory by using the following command:

    ```
    rm -R /var/atlas
    ```

    **Notes:**

    -   You might need super user authority to run this command.
    -   You must identify the Atlas installation directory correctly. Running a recursive remove command with the wrong directory name might delete critical files.

**Parent topic:** [Installing Atlas](../topics/install.md)
