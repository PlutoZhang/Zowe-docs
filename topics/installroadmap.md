# Installation roadmap

Installing Project Zoe involves several steps that you must complete in the appropriate sequence. Review the following installation roadmap that presents the task-flow for preparing your environment and installing and configuring Project Zoe before you begin the installation process.

| Tasks | Description
| --- | ---
| 1. Prepare your environment to meet the installation requirements. | See [System requirements](planinstall.md).
| 2. Obtain the Zoe installation files. | The Zoe installation files are released in a PAX file format. The PAX file contains the runtimes and the scripts to install and launch the z/OS runtime, as well as the Zoe Brightside package. For information about how to download, prepare, and install the Zoe runtime, see [Obtaining the installation files](zoegettingstarted.md).
| 3. Allocate enough space for the installation. |  The installation process requires approximately 1 GB of available space. Once installed on z/OS, API Mediation Layer requires approximately 150MB of space, zLUX requires approximately 50 MB of space before configuration, and explorer server requires approximately 200 MB. Zoe Brightside requires approximately 200 MB of space on your PC.
| 4. Install components of Project Zoe. | To install Zoe runtime (zLUX, explorer server, and API Mediation Layer) on z/OS, see [Installing the Zoe runtime on z/OS](zoeinstall.md). To install Zoe Brightside on PC, see [Installing Zoe Brightside](cli-installcli.md).
| 5. Verify that Project Zoe is installed correctly. | To verify that API Mediation Layer, zLUX, and explorer server are installed correctly, see [Verifying installation](verify.md). To verify that Zoe Brightside is installed correctly, see [Testing connection to z/OSMF](cli-validateInstallation.md).
| 6. Optional: Troubleshoot problems that occurred during installation. | See  [Troubleshooting installing the Zoe runtime](zoeinstalltroubleshoot.md) and [Troubleshooting installing Zoe Brightside](cli-troubleshootinginstallingcli.md).

To uninstall Project Zoe, see [Uninstalling Project Zoe](uninstall.md).
