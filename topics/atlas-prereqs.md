# Prerequisites for explorer server

Before installing the explorer server, check whether your environment meets the following requirements to ensure a successful installation.

-   The explorer server must be installed on z/OS® Version 2.2 or later.
-   The explorer server requires a 64-bit Java™ 8 JRE or later.
-   [IBM® z/OS Management Facility \(z/OSMF\)](https://www.ibm.com/support/knowledgecenter/en/SSLTBW_2.3.0/com.ibm.zos.v2r3.izu/izu.htm) must be installed and running. z/OSMF is a prerequisite for the explorer server microservice. For details, see [Prerequisites for z/OSMF configuration](topics/prezosmf.md).
-   \(Optional\) To enable real-time access to SYSLOG, SDSF must be installed.

## Pre-installation checklist

The following information is required during the installation process. Make the decisions before you install the explorer server.

-   The HFS directory where you install the explorer server, for example, `/var/atlas`.
-   The HFS directory path that contains a 64-bit Java™ 8 JRE.
-   The z/OSMF installation directory `/lib` that contains `derby.jar`, for example, `/usr/lpp/zosmf/lib`.
-   The z/OSMF configuration user directory path that contains z/OSMF `/bootstrap.properties`, `/jvm.security.override.properties`, and `/resources/security/ltpa.keys files`.
-   The explorer server HTTP and HTTPS port numbers. By default, they are 7080 and 7443.
-   The user ID that runs the Liberty explorer server started task.

    **Tip:** Use the same user ID that runs the z/OSMF IZUSVR1 task, or a user ID with equivalent authorizations.

-   \(Optional\) The SDSF Java installation directory, for example, `/usr/lpp/sdsf/java`.
