# System requirements

Before installing Atlas, check whether your environment meets the following requirements to ensure a successful installation.

-   Atlas must be installed on z/OS® version 2.1 or later.
-   [IBM® z/OS Management Facility \(z/OSMF\)](https://www.ibm.com/support/knowledgecenter/en/SSLTBW_2.3.0/com.ibm.zos.v2r3.izu/izu.htm) must be installed and running. z/OSMF is a prerequisite for the Atlas microservice.

    Atlas uses the RESTFILES and RESTJOBS services of z/OSMF to access data sets, z/OS UNIX™ System Services \(USS\) files, and job spool files. Therefore, these services must be correctly configured and available when Atlas is running.

    Additionally, Atlas uses z/OSMF configuration by using symbolic links to the z/OSMF `bootstrap.properties`, `jvm.security.override.properties`, and the ltpa.keys files. Specifically, Atlas reuses z/OSMF's SAF, SSL, and LTPA configuration; therefore, these configurations must be valid and complete to operate Atlas successfully.

    For more information about z/OSMF installation and customization, see the IBM z/OS Management Facility Configuration Guide \(SC27-8419\).

-   \(Optional\) To enable real-time access to SYSLOG, SDSF must be installed.

**Parent topic:** [Planning the installation](../topics/planinstall.md)
