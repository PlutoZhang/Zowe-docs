# Uninstalling explorer server

To uninstall the explorer server, take the following steps:

1.  Stop your Explorer Liberty server by running the following operator command:

    ```
    C ZOESVR
    ```

2.  Delete the ZOESVR member from your system PROCLIB data set.
3.  Remove RACF® \(or equivalent\) definitions with the following command:

    ```
    RDELETE STARTED (ZOESVR.*)
    SETR RACLIST(STARTED) REFRESH
    REMOVE (userid) GROUP(IZUUSER)
    ```

4.  Delete the z/OS® UNIX™ System Services explorer server directory and files from the explorer server installation directory by issuing the following command:

    ```sh
    rm -R /var/atlas #*Atlas Installation Directory*
    ```

    **Notes:**

    -   You might need super user authority to run this command.
    -   You must identify the explorer server installation directory correctly. Running a recursive remove command with the wrong directory name might delete critical files.
