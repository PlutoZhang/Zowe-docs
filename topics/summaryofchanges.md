# Summary of changes

Learn about what is new, changed, and removed in Project Zoe.

## Version 0.8.2 (June 2018)

### What's new

**zLUX**

- zLUX application plug-in definition and Configuration Dataservices

   - Information about the plug-in definition file and the zLUX application plug-in filesystem structure was added. [Learn more](mvd-zluxplugindefandstruct.md).
   - Information about Configuration Dataservices that enable you to set plug-in default behavior was added. [Learn more](mvd-configdataservice.md)

- zLUX terminal application plug-in initial configuration steps

  Steps to initially configure the zLUX terminal application plug-ins were added. [Learn more](mvd-configterminalappports.md).

**Zoe Brightside**

- Zoe Brightside is now built on a framework that lets you install plug-ins to extend the capabilities of the product. You can install the following plug-ins for Zoe Brightside:
   - Zoe Brightside plug-in for CA Endevor® Software Change Manager
   - Zoe Brightside plug-in for CA File Master™ Plus
   - Zoe Brightside plug-in for IBM® Db2® Database   

   For more information, see [Extending Zoe Brightside](cli-extending.md).

   The new framework also improves the stability and quality of Zoe Brightside.

- You can now install Zoe Brightside using simplified and flexible installation process. You can now install Zoe Brightside using either of the following methods:
    - Install Zoe Brightside using the installation package that is contained on the Project Zoe Downloads repository.
    - Install Zoe Brightside using the Node.js Package Manager (npm).

    **Important!** Both of the installation methods require Internet access on client PCs.

   For more information, see [Installing Zoe Brightside](cli-installcli.md).

### What's changed

**Installation procedure**

- zLUX and explorer server installation
    - Added RACF authorization for Zoe.
    - Zoe start and stop are now available as shell scripts that you can issue from the USS command line without using TSO LOGON and SDSF.
    - You can now start and stop zLUX server, explorer server, and zSS server together.
    - The JCL for the Zoe server started task is now _automatically_ copied to a suitable PROCLIB.
    - The install script now writes a date-time-stamped log as it runs, which you can use for debugging or reference.

- Zoe Brightside installation

**Zoe Brightside**

- **CA Brightside** was renamed to **Zoe Brightside**.


### What's removed:

**Zoe Brightside**

Experimental command groups have been removed from Zoe Brightside.

## Version 0.8.1 (May 2018)

### What's new
**VT Terminal**

  zLUX now provides a VT Terminal application plug-in that provides a connection to USS and UNIX. [Learn more](mvd-appplugins.md).

### What's changed
**Product naming**

  Project Giza is renamed to Project Zoe. Atlas is renamed to explorer server.

**Installation procedure**

  Project Zoe now provides an enhanced and simplified installation process to improve your installation experience. [Learn more](zoeinstall.md).
