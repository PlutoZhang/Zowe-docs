# Verifying zLUX installation

If zLUX is installed correctly, you can open the MVD from a supported browser. 

From a supported browser, open the MVD at `https://myhost:httpsPort/ZLUX/plugins/com.rs.mvd/web/index.html`
    
where:

-   *myHost* is the host on which you are running the Zoe Node Server.
-   *httpPort* is the value that was assigned to `node.http.port` in `zluxserver.json`.
-   *httpsPort* is the value that was assigned to *node.https.port* in `zluxserver.json`.
    For example, if you run the Zoe Node Server on host *myhost* and the value that is assigned to *node.http.port* in `zluxserver.json` is 12345, you would specify `https://myhost:12345/ZLUX/plugins/com.rs.mvd/web/index.htm`.

