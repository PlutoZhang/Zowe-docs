# Verifying zLUX installation

If zLUX is installed correctly, you can open the MVD from a supported browser.

From a supported browser, open the MVD at `https://myhost:httpsPort/ZLUX/plugins/com.rs.mvd/web/index.html`

where:

* _myHost_ is the host on which you installed the Zoe Node Server.
* _httpPort_ is the port number that was assigned to `node.http.port` in `zluxserver.json`.
* _httpsPort_ is the port number that was assigned to _node.https.port_ in `zluxserver.json`.

  For example, if the Zoe Node Server is installed on host _myhost_ and the port number that is assigned to the HTTP port is 12345, you specify `https://myhost:12345/ZLUX/plugins/com.rs.mvd/web/index.htm`.

