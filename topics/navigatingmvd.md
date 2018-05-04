# Navigating MVD


From the Mainframe Virtual Desktop (MVD), you can access the Project Giza applications. 

## Accessing the MVD

From a supported browser, open the MVD at `https://myhost:httpsPort/ZLUX/plugins/com.rs.mvd/web/index.html`
    
where:

-   *myHost* is the host on which you are running the Giza Node server.
-   *httpPort* is the value that was assigned to `node.http.port` in `zluxserver.json`.
-   *httpsPort* is the value that was assigned to *node.https.port* in `zluxserver.json`.
    For example, if you run the Giza Node Server on host *myhost* and the value that is assigned to *node.http.port* in `zluxserver.json` is 12345, you would specify `https://myhost:12345/ZLUX/plugins/com.rs.mvd/web/index.htm`.


## Logging into and out of the MVD

1. To log in, enter your mainframe credentials in the **Username** and  **Password** fields.
2. Press Enter. Upon authentication of your user name and password, the desktop opens.

To log out, click the the avatar in the lower right corner and click **Sign Out**.
