# Uninstalling API Mediation Layer

You can uninstall API Mediation Layer when you no longer want to use the product.

**Note:** Be aware of the following considerations:

-   You might need super user authority to run this command.
-   You must identify the API Mediation installation directory correctly. Running a recursive remove command with the wrong directory name can delete critical files.

**Follow these steps:**

1.  Stop your API Mediation services by running the following operator command:

    ```
    C ZOESVR
    ```

2.  Delete the `ZOESVR` member from your system `PROCLIB` data set.
3.  Remove RACF® \(or equivalent\) definitions with the following command:

    ```
    RDELETE STARTED (ZOESVR.*)
    SETR RACLIST(STARTED) REFRESH
    REMOVE (userid) GROUP(IZUUSER)
    ```

4.  Delete the z/OS® UNIX™ System Services API Mediation directory and files from the API Mediation installation directory by issuing the following command:

    ```sh
    rm -R /var/zoe_install_directory/api-mediation #*Zoe Installation Directory*
    ```


