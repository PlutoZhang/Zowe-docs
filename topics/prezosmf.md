# Prerequisites for z/OSMF configuration

IBM z/OS Management Facility (z/OSMF) is a prerequisite for the Giza microservice. It must be installed and running before using Giza.

Giza uses the RESTFILES and RESTJOBS services of z/OSMF to access data sets,
z/OS UNIX System Services (UNIX System Services) files, and JES job spool files.
Therefore, these services must be correctly configured and available when Giza
is running.

Additionally, Giza uses z/OSMF configuration by using symbolic links to the
z/OSMF `bootstrap.properties`, `jvm.security.override.properties`, and the
`ltpa.keys` files. Specifically, Giza reuses z/OSMF's SAF, SSL, and LTPA
configuration; therefore, these configurations must be valid and complete to
operate Giza successfully.

The z/OSMF product is required for Giza to run. The z/OSMF process differs
depending on whether you have z/OS v2.2 or v2.3.

Verify your system requirements:

1. For z/OS v2.2 or later, use any of the following options to determine which version is installed:
   - If you have access to the console, for example, in SDSF, issue the command:
      ```
      /D IPLINFO
      ```
      Part of the output contains the release, for example,

      `RELEASE z/OS 02.02.00.`

   - If you don't have access to the console, use SDSF and select the menu option **MAS**. Two columns of the output show the SysName (LPAR name) and the z/OS version, for example:

     `SysName  Version`

     `S001     z/OS 2.2`

     Identify the z/OS Version for the LPAR on which you are going to use z/OSMF.

   - If you don't have access to SDSF, use ISPF option **7.3** (Dialog Test Variables) and scroll down to the
        variable `ZOS390RL`, for example,

        `ZOS390RL S N z/OS   02.02.00`

   - On the ISPF Primary Option Menu, the last entry is the ISPF Release, which corresponds to the z/OS version as follows:

     Release . : ISPF 7.1    --> z/OS v2.1

     Release . : ISPF 7.2    --> z/OS v2.2

     Release . : ISPF 7.3    --> z/OS v2.3

2. For z/OS V2.2 users, take the following steps:

   z/OSMF is a base element of z/OS v2.2 and v2.3, so it should already be installed. However, it is not guaranteed to be configured and running on every z/OS V2.2 and V2.3 system.

   Configuring an instance of z/OSMF is done by running the IBM-supplied jobs IZUSEC and IZUMKFS, and then starting the z/OSMF server in the following order:
   1. Security setup (the IZUSEC job)
   2. Configuration (the IZUMKFS job)
   3. Server initialization (the START command)

3. For z/OS V2.3 users, be aware of the following notes:

   In z/OS V2R3, the base element z/OSMF is started by default at system IPL. This means that z/OSMF is available for use as soon as the system is up. If you prefer not to have z/OSMF started automatically, you can disable the autostart function by checking for `START` commands for the z/OSMF started procedures in the COMMNDxx parmlib member.

   The z/OS Operator Consoles task is new in this release. Applications that depend on access to the operator console such as Brightside's RestConsoles API require version 2.3.

4. Other requirements
   1. Perform any maintenance that is required by Node.js.

      Connect to your target z/OS system, for example, with ssh to port 22 to get a USS command window. Issue the command:
      ```
      node -v
      ```
      The response should be:

       `v6.11.2`

      or later. If the version displayed is not right, set and/or download the right version of node by using npm and nvm. You might want to refer to the following links for tutorials on npm and nvm:

      https://www.sitepoint.com/beginners-guide-node-package-manager/
      https://www.sitepoint.com/quick-tip-multiple-versions-node-nvm/

      If you don’t have node installed, go to https://nodejs.org/en/download/package-manager/, select your operating system, and follow the instructions to install node. Ensure that you download only official versions of these products. For z/OSMF, you need only one version of node.js. You can find the complete procedure for installing Node.js at https://developer.ibm.com/node/sdk/ztp/.

      When completed, set the `NODE_HOME` environment variable to the directory where your Node.js is installed, for example,
      ```
      NODE_HOME=/proj/mvd/node/installs/node-v6.10.3-os390-s390x
      ```
   2. Issue the following command to check the Java installation.
   ```
   java -version
   ```
   The response should be

    `java version "1.8.0"`

     or later. If the version displayed is not right, set the `JAVA_HOME` variable to point to the preferred java version. If the preferred java version is not installed, install it.

   3. Verify that you have 400 MB of free HFS file space for the installation. You can use the `df` command to check the available space in your chosen file system, for example,
   ```
   df -k /usr/lpp/zosmf
   ```
   The output should be as follows:

      Mounted on            Filesystem               Avail/Total

      /Z22C/usr/lpp/zosmf  (ZFS.S001.Z22C.ZOSMF)      26711/535680

     From the output above, you can see that only 26.711 MB is available (because z/OSMF is already installed), but the total in that file system is 535.68 MB, so enough space was available when the file system was created.

   4. Verify your browser support.

      Confirm that the machine from which you plan to run the Giza desktop runs one of the supported browsers:
     - Chrome version 54 or later
     - Firefox version 44 or later
     - Microsoft Edge

     **Note**: Microsoft Internet Explorer is not yet supported at any version.

   5. After configuring z/OSMF, verify the following items to ensure z/OSMF is ready for Giza.

      Check that the z/OSMF server and angel processes are running. From SDSF on z/OS, use the `DA` command or issue the following command on the command input line:
      ```
      /D A,IZU*
      ```
      If you don't see jobs like IZUANG1 and IZUSVR1 active, start the angel process with the following command:
      ```
      /S IZUANG1
      ```
      When you see the message **CWWKB0056I INITIALIZATION COMPLETE FOR ANGEL**, start the server with the following command:
      ```
      /S IZUSVR1
      ```
      The server might take a couple of minutes to fully initialize. The z/OSMF server is available when the following message **CWWKF0011I: The server zosmfServer is ready to run a smarter planet.** is displayed.

      You can test z/OSMF with your browser by first finding the startup messages in the SDSF log of the z/OSMF server by using the following find command:
      ```
      f IZUG349I
      ```

      You should see these lines:

      `IZUG349I: The z/OSMF STANDALONE Server home page can be accessed at`

        `: https://mvs.hursley.ibm.com:443/zosmf`

        `: after the z/OSMF server is started on your system.`

      From the lines above, the port number is 443. You will need this later.

      Point your browser at the nominated z/OSMF STANDALONE Server home page and you should see its Welcome Page where you can log in.

      To verify that z/OSMF is working correctly, use any of the following ways:
      - Use the Brightside CLI by following these steps:

        1. Install Brightside on your local desktop.
           1. Navigate to the supplied Giza folder with brightside artifacts.
           2. Download brightside-0.6.5-17.tgz to a folder on your PC/Mac and open a terminal and navigate to the folder.
           3. Check that you have node installed by typing `node –v`.
           4. Once you have node installed then type `npm install –g <file-name>`. Brightside will be installed and you will see some progress bars.
           5. Verify the installation by typing bright `–h`.
        2. Create a Brightside profile.

           On a Windows system, issue a command like this:
           ```
           bright zosmf create bright-profile -H <hostname> -P <port>
           -u <userid> -p <password> -a GIZA --bpn brightprof
           ```
           You should see response as follows:

             Brightside CLI profile created successfully! Path:
             C:\Users\IBM_ADMIN\.brightside\profiles\zosmf\brightprof.yaml

             module:             zosmf
             host:               <hostname>
             port:               <port>
             version:            1.0
             user:               <userid>
             rejectUnauthorized: false
             logonProc:          IZUFPROC
             account:            GIZA
             auth:               <auth string>
             profileName:        brightprof

           You can get context-sensitive help for any Brightside command by appending `-h` to it. For example,

           ```
           bright zosmf create bright-profile -h
           ```

        3. Run the Brightside IVT.

           Before your run the IVT, check that JES2 is accepting jobs with `CLASS=C` by issuing the following command in SDSF:
           ```
           /$D I
           ```
           You will see responses like this in SYSLOG:
           ```
           $HASP892 INIT(3)   STATUS=ACTIVE,CLASS=AB,...
           ```
           If none of the initiators has **C** in its CLASS list, add **C** to the list of any initiator, for example, initiator 3 as shown above, with this command:
           ```
           /$T I3,CL=ABC
           ```
           Run the Brightside IVT from your desktop:

           ```
           bright zosmf validate prof --zosmf-p brightprof
           ```
           This will run 10 tests and produce a table of results.

      - Type the REST endpoint into your browser, for example:
          https://mvs.ibm.com:443/zosmf/restjobs/jobs

          Browsing zosmf endpoints asks for your user ID and password for defaultRealm; these are your TSO user credentials.

          Your browser should return you a status code 200 with a list of all jobs on your z/OS system. The list is in raw JSON format.

**References:**

z/OSMF for v2.2:

- [IBM z/OS Management Facility Help](https://www.ibm.com/support/knowledgecenter/SSLTBW_2.2.0/com.ibm.zos.v2r2.izu/izu.htm)

- [IBM z/OS Management Facility Configuration Guide]( https://www.ibm.com/support/knowledgecenter/en/SSLTBW_2.2.0/com.ibm.zos.v2r2.izua300/IZUHPINFO_PartConfiguring.htm)


z/OSMF for v2.3:

- [IBM z/OS Management Facility Help](https://www.ibm.com/support/knowledgecenter/SSLTBW_2.3.0/com.ibm.zos.v2r3.izu/izu.htm)

- [IBM z/OS Management Facility Configuration Guide](https://www.ibm.com/support/knowledgecenter/en/SSLTBW_2.3.0/com.ibm.zos.v2r3.izua300/IZUHPINFO_PartConfiguring.htm)




**Parent topic:** [Prerequisites](../topics/planinstall.md)
