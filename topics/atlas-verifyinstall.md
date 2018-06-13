# Verifying explorer server installation

After explorer server is installed and the FEKATLS procedure is started, you can verify the installation from an Internet browser by using the following case-sensitive URL:

https://<your.server>:<atlasport>/Atlas/api/system/version

where *your.server* is the host name or IP address of the z/OS® system where explorer server is installed, and *atlasport* is the port number that is chosen during installation. You can verify the port number in the `server.xml` file that is located in the explorer server installation directory, which is `/var/atlas/wlp/usr/servers/Atlas/server.xml`by default. Look for the `httpsPort` assignment in the `server.xml` file, for example: httpPort="7443".

This URL sends an HTTP GET request to the Liberty Profile explorer server. If explorer server is installed correctly, a JSON payload that indicates the current explorer server application version is returned. For example:

```
{ "version": "V0.0.1" }
```

**Note:** The first time that you interact with the explorer server, you are prompted to enter an MVS™ user ID and password. The MVS user ID and password are passed over the secure HTTPS connection to establish authentication.

After you verify that explorer server was successfully installed, you can access the UI at:

https://<your.server>:<atlasport>/ui/\#/

If explorer server is not installed successfully, see [Troubleshooting installation](troubleshoot.md) for solutions.

## Verifying the availability of explorer server REST APIs

To verify the availability of all explorer server REST APIs, use the Liberty Profile's REST API discovery feature from an internet browser with the following URL. This URL is case-sensitive.

https://<your.server>:<atlasport>/ibm/api/explorer

With the discovery feature, you can also try each discovered API. The users who verify the availability must have access to their data sets and job information by using relevant explorer server APIs. This ensures that your z/OSMF configuration is valid, complete, and compatible with the explorer server application. For example, try the following APIs:

 Explorer server: JES Jobs APIs

       `GET  /Atlas/api/jobs`

       This API returns job information for the calling user.

 Explorer server: Data set APIs  

       `GET /Atlas/api/datasets/userid.**`  

       This API returns a list of the userid.** MVS data sets.
