# Installing Project Giza

This topic contains instructions for downloading and installing Project Giza.

## Obtaining Project Giza installation media

To download and unpack the installation media, follow these steps:

1. Go to the [Project Giza download page](https://github.com/gizafoundation/Downloads/releases) in GitHub.
2. Click the file with the `.pax` extension (for example, project_giza-0_8_0.pax) and save the file to your preferred location.
3. Transfer the PAX file as-is to the USS file system on the mainframe using FTP in binary mode or SFTP.

   **Note:** SCP will not transfer correctly as the PAX file must be binary, not txt transferred.
4. Unpack the PAX file by issuing the following command.  
   ```
   pax -ppx -rf <pax-file-name>.pax
   ```  
   Where _pax-file-name_ is a variable that indicates the name of the PAX file you downloaded.

## Installation overview

To install Project Giza, follow these steps:  

1. Prepare your environment to meet the installation requirements. For details, see [Prerequisites](../topics/planinstall.md).

2. Allocate enough space for the installation.

     For successful installation of Project Giza, your PC must contain the required space. The installation process requires approximately 1 GB of available space. Once installed, zLUX requires approximately 50 MB of space before configuration, Atlas requires approximately 200 MB, and Brightside CLI requires approximately 25 MB.

3. Install components of Project Giza. For details, see [Installing components of Project Giza](../topics/installing.md).

4. Verify that Project Giza is installed correctly. For details, see [Verifying Installation](../topics/verifyinstall.md).

For problems that might occur during an installation and how to resolve them, see [Troubleshooting installation](../topics/troubleshoot.md).

To uninstall Project Giza, see [Uninstalling Project Giza](../topics/uninstallingatlas.md).
