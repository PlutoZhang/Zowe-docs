# Installing Zoe

The Zoe packages are distributed as a PAX file that contains the runtimes and the scripts to install and launch the z/OS runtime and the runtime for the desktop command line interface.

After you obtain the Zoe PAX file from the [Zoe download page](https://github.com/gizafoundation/Downloads/releases) in GitHub and save the file to your preferred location, follow these steps to transfer and expand the Zoe PAX file:

1. Transfer the PAX file to z/OS.

    a. Navigate your desktop PC or Mac where you have the Zoe PAX file in your folder.

    b. Connect to z/OS using SFTP. Issue the following command:

     ```
     sftp <userIDorip.of.zos.box>
     ```

     If SFTP is not available or if you prefer to use FTP, you can issue the following command instead:

     ```
     ftp <userID@ip.of.zos.box>
     ```

     **Note**: When you use FTP, do not transfer the PAX file in txt mode because this will corrupt the contents of the PAX file. Instead, switch to binary file transfer mode by issuing the following command:

     ```
     bin
     ```

    c. Navigate to the target directory on z/OS.

    After you connect to z/OS and enter your password, you will be entered into the Unix file system. Navigate to the directory you wish to transfer the Zoe PAX file into.
    
     - To see what directory you are in, type `pwd`.
     - To switch directory, type `cd`.
     - To list the contents of a directory, type `ls`.
     - To create a directory, type `mkdir`.  

    d. When you are in the directory you want to transfer the Zoe PAX file into, issue the following command:

     ```
     put <pax-file-name>.pax
     ```

    Where _pax-file-name_ is a variable that indicates the full name of the PAX file you downloaded. For example, zoe-0.8.1.pax.

2. When the PAX file has transferred, expand the PAX file by issuing the following command.  

    ```
    pax -ppx -rf <pax-file-name>.pax
    ```  

    Where _pax-file-name_ is a variable that indicates the name of the PAX file you downloaded. For example, zoe-0.8.1.pax.

    This will expand to a file structure.

    ```
      /files
      /install
      /scripts
      ...
    ```
     **Note**: pax will expand into the current directory.  A good practice is to keep the install directory apart from the install direectory.  This can be done by creating a directory such as /zoe/builds that contains the pax files, and another such as /zoe/drivers/.  Put the zoe-0.8.1.pax into /zoe/builds, create a folder such as /zoe/drivers/0.8.1, cd into this folder and run pax -ppf -rf ../../builds/zoe-0.8.1.pax