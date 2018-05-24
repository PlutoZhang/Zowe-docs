# Verifying explorer server installation

After explorer server is installed and the FEKATLS procedure is started, you can verify the installation from an Internet browser by using the following URL:

https://*your.server*:*atlasport*/Atlas/api/system/version

where *your.server* matches the host name or IP address of your z/OS® system where explorer server is installed, and *atlasport* matches the port number that is chosen during installation. You can verify the port number in the server.xml file that is located in the explorer server installation directory, which is */var/atlas/wlp/usr/servers/Atlas/server.xml* by default. Look for the httpsPort assignment in the *server.xml* file, for example: httpPort="7443".

**Important:** This URL is case-sensitive.

This URL sends an HTTP GET request to your Liberty Profile explorer server. If explorer server is installed correctly, a JSON payload that indicates the current explorer server application version is returned. For example:

```
{ "version": "V0.0.1" }
```

**Note:** For the first interaction with the explorer server, you are prompted to enter an MVS™ user ID and password. The MVS user ID and password are passed over the secure HTTPS connection to establish authentication.

After you verify that explorer server was successfully installed, you can access the UI at:

https://*your.server:atlasport*/ui/\#/

## Verifying the availability of explorer server REST APIs

To verify the availability of all explorer server REST APIs, use the Liberty Profile's REST API discovery feature from an internet browser with the following URL:

https://*your.server:atlasport*/ibm/api/explorer

**Note:** This URL is case-sensitive.

With the discovery feature, you can also try each discovered API. The users who verify the availability must have access to their data sets and job information by using relevant explorer server APIs. This ensures that your z/OSMF configuration is valid, complete, and compatible with the explorer server application. For example, try the following APIs:

 Explorer server: JES Jobs APIs

       `GET  /Atlas/api/jobs`

       This API returns job information for the calling user.

 Explorer server: Data set APIs  

       `GET /Atlas/api/datasets/userid.**`  

       This API returns a list of the userid.** MVS data sets.

If explorer server is not installed successfully, see [Troubleshooting installation](troubleshoot.md) for solutions.
