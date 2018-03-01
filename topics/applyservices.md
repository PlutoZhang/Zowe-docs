# Applying services to Atlas

You can monitor IBM® [Mainframe Developer Center](https://developer.ibm.com/mainframe/products/atlas/) for service availability of Atlas. When maintenance is available, you can apply the service to Atlas by replacing either the EAR file only or the whole service package.

To replace the EAR file, take the following steps:

1.  Download the EAR file from the download site as a .zip file.
2.  Extract the EAR package on your personal machine or by using zip utilities on the mainframe.
3.  Stop the existing instance of the Atlas server.
4.  Backup and delete the existing EAR file located at *"\{server root folder\}/wlp/usr/servers/Atlas/apps"*.
5.  Transfer the new EAR file to the server at the same location *"\{server root folder\}/wlp/usr/servers/Atlas/apps"*.
6.  Restart the Atlas server.

To replace the whole service package, take the following steps:

1.  Transfer the maintenance archive to your z/OS® system in binary mode.
2.  Unpack the archive in your Atlas installation directory in z/OS UNIX™ System Services. Or, run the install script that is provided in the archive if any.
3.  Stop and restart your Atlas Liberty server.

    **Note:** By default, Atlas server configuration switches off application monitoring in the Liberty server.xml file. For "hot deploy", you can remove this setting in the server.xml file to avoid the need to stop and restart your Atlas server. For more information, see WebSphere® Liberty Profile documentation.


After restarting the Atlas server, you can check the version of Atlas that you installed from the swagger interface, which is `Atlas/api/system/version` under System APIs.

**Parent topic:** [Installing Atlas](../topics/install.md)
