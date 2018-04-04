# Installing components of Project Giza

## Obtain the Project Giza installation media
Download the Project Giza installation media and transfer the files to client workstations to begin using the product at your site.

**Follow these steps:**

1. To download the installation media, click the [project_giza-0_8_0.pax](https://github.com/gizafoundation/Downloads/releases/download/v0.8.0/project_giza-0.8.0.pax) file.
2. After you download the pax file, transfer it as-is to the USS file system on the mainframe using, FTP in binary mode or sftp (note that scp will not transfer correctly as the pax file must be binary, not txt transferred).
3. Unpack the pax file using "pax -ppx -rf project_giza-0.8.0.pax" and follow the install instructions in the user guide project_giza_0.8.0_user_guide.pdf

**Note:** The installation process will require approximately 4GB of available space. Once installed, zLUX requires approximately 870 MB of space, Atlas requires approximately 200MB, and Brightside CLI requires approximately 25 MB.

**Important!** Before you install the components of Project Giza, ensure that you meet [the prerequisites](planinstall.md).

Follow the procedures in this section to install the components of Project Giza.

-   **[Installing zLUX](../topics/installvirtualdesktop.md)**
-   **[Installing Atlas](../topics/atlas-install.md)**
-   **[Installing Brightside CLI](../topics/cli-installcli.md)**
