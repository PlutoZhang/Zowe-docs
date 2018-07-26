# Navigating MVD

From the Mainframe Virtual Desktop \(MVD\), you can access the Project Zoe applications.

## Accessing the MVD

From a supported browser, open the MVD at `https://myhost:httpsPort/ZLUX/plugins/com.rs.mvd/web/index.html`

where:

* _myHost_ is the host on which you are running the Zoe Node Server.
* _httpsPort_ is the value that was assigned to _node.https.port_ in `zluxserver.json`.

  For example, if you run the Zoe Node Server on host _myhost_ and the value that is assigned to _node.https.port_ in `zluxserver.json` is 12345, you would specify `https://myhost:12345/ZLUX/plugins/com.rs.mvd/web/index.html`.

## Logging in and out of the MVD

1. To log in, enter your mainframe credentials in the **Username** and  **Password** fields.
2. Press Enter. Upon authentication of your user name and password, the desktop opens.

To log out, click the the avatar in the lower right corner and click **Sign Out**.

