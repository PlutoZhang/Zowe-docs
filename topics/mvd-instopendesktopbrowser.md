# Verifying zLUX installation

If zLUX is installed correctly, you can open the MVD from a supported browser. 

From a supported browser, open the MVD at `https://myhost:httpsPort/ZLUX/plugins/com.rs.mvd/web/index.html`
    
where:

-   *myHost* is the host on which you installed the Zoe Node Server.
-   *httpPort* is the port number that was assigned to `node.http.port` in `zluxserver.json`.
-   *httpsPort* is the port number that was assigned to *node.https.port* in `zluxserver.json`.
    For example, if the Zoe Node Server is installed on host *myhost* and the port number that is assigned to the HTTP port is 12345, you specify `https://myhost:12345/ZLUX/plugins/com.rs.mvd/web/index.htm`.

