# Pre-installation checklist

The following information is required during the installation process. Make the decisions before you install Atlas.

-   The HFS directory where you install Atlas, for example, `/var/atlas`.
-   The HFS directory path that contains a 64-bit Java™ 8 JRE.
-   The z/OSMF installation directory /lib that contains `derby.jar`, for example, `/usr/lpp/zosmf/lib`.
-   The z/OSMF configuration user directory path that contains z/OSMF `/bootstrap.properties`, `/jvm.security.override.properties`, and `/resources/security/ltpa.keys files`.
-   The Atlas http and https port numbers. By default, they are 7080 and 7443.
-   The user ID that runs the Liberty Atlas started task.

    **Tip:** Use the same user ID that runs the z/OSMF IZUSVR1 task, or a user ID with equivalent authorizations.

-   \(Optional\) The SDSF java installation directory, for example, `/usr/lpp/sdsf/java`.

**Parent topic:** [Planning the installation](../topics/planinstall.md)
