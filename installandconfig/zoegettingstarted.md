# Obtaining installation files

The Zoe installation files are distributed as a PAX file that contains the runtimes and the scripts to install and launch the z/OS runtime and the runtime for the command line interface.

To obtain a Zoe PAX file, visit [Zoe download page](https://github.com/gizafoundation/Downloads/releases) in GitHub. For each release, there is a PAX file named `project_zoe-v.r.m.pax`, where

* `v` indicates the version
* `r` indicates the release number
* `m` indicates the modification number

The numbers are incremented each time a release is created so the higher the numbers, the later the release. Use your web browser to download the PAX file by saving it to a folder on your desktop.

Follow these steps to transfer the PAX file to z/OS and prepare it to install the Zoe runtime.

1. Transfer the PAX file to z/OS.

   a. Open a terminal in Mac OS/X, or command prompt in Windows OS, and navigate to the directory where you downloaded the Zoe PAX file.

   b. Connect to z/OS using SFTP. Issue the following command:

   ```text
     sftp <userID@ip.of.zos.box>
   ```

   If SFTP is not available or if you prefer to use FTP, you can issue the following command instead:

   ```text
     ftp <userID@ip.of.zos.box>
   ```

   **Note**: When you use FTP, switch to binary file transfer mode by issuing the following command:

   ```text
     bin
   ```

   c. Navigate to the target directory on z/OS.

   ```text
   After you connect to z/OS and enter your password, you will be entered into the Unix file system. Navigate to the directory you wish to transfer the Zoe PAX file into.

   - To see what directory you are in, type `pwd`.
   - To switch directory, type `cd`.
   - To list the contents of a directory, type `ls`.
   - To create a directory, type `mkdir`.   
   ```

   d. When you are in the directory you want to transfer the Zoe PAX file into, issue the following command:

   ```text
     put <pax-file-name>.pax
   ```

   Where _pax-file-name_ is a variable that indicates the full name of the PAX file you downloaded. For example, zoe-0.8.1.pax.

   **Note**: When your terminal is connected to z/OS through FTP or SFTP, you can prepend commands with `l` to have them issued against your desktop. To list the contents of a directory on your desktop, type `lls` where `ls` will list contents of a directory on z/OS.

2. When the PAX file has transferred, expand the PAX file by issuing the following command in an ssh session:

   ```text
    pax -ppx -rf <pax-file-name>.pax
   ```

   Where _pax-file-name_ is a variable that indicates the name of the PAX file you downloaded. For example, zoe-0.8.1.pax.

```text
This will expand to a file structure.

```
  /files
  /install
  /scripts
  ...
```

 **Note**: The PAX file will expand into the current directory. A good practice is to keep the installation directory apart from the directory that contains the PAX file.  To do this, you can create a directory such as /zoe/paxes that contains the PAX files, and another such as /zoe/builds.  Use SFTP to transfer the Zoe PAX file into the /zoe/paxes directory, use the `cd` command to switch into /zoe/builds and run the command `pax -ppx -rf ../../paxes/<zoe-v.r.m>.pax`.  The /install folder will be created inside the zoe/builds directory from where the install can be launched.
```

