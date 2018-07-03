# Troubleshooting installing explorer server

If explorer server REST APIs do not work, check the following items:

-   Check whether your Liberty explorer server is running.

    You can check this in the Display Active \(DA\) panel of SDSF under ISPF. The ZOESVR started task should be running. If the ZOESVR task is not running, start the explorer server by using the following `START` operator command:

    ```
    /S ZOESVR
    ```

    You can also use the operator command `/D A,ZOESVR` to verify whether the task is active, which alleviates the need for the \(DA\) panel of SDSF. If the started task is not running, ensure that your ZOESVR procedure resides in a valid PROCLIB data set, and check the task’s job output for errors.

-   Check whether the explorer server is started without errors.

    In the Display Active \(DA\) panel of SDSF under ISPF, select the ZOESVR job to view the started task output. If the explorer server is started without errors, you can see the following messages:

    ```
    CWWKE0001I: The server Atlas has been launched.
    ```

    ```
    CWWKF0011I: The server Atlas is ready to run a smarter planet.
    ```

    If you see error messages that are prefixed with "ERROR" or stack traces in the ZOESVR job output, respond to them.

-   Check whether the URL that you use to call explorer server REST APIs is correct. For example: https://your.server:atlasport/Atlas/api/system/version. The URL is case-sensitive.
-   Ensure that you enter a valid z/OS® user ID and password when initially connecting to the explorer server.
-   If testing the explorer server REST API for jobs information fails, check the z/OSMF IZUSVR1 task output for errors. If no errors occur, you can see the following messages in the IZUSVR1 job output:

    ```
    CWWKE0001I : The server zosmfServer has been launched.
    ```

    ```
    CWWKF0011I: The server zosmfServer is ready to run a smarter planet.
    ```

    If you see error messages, respond to them.

    For RESTJOBS, you can see the following message if no errors occur:

    ```
    CWWKZ0001I: Application IzuManagementFacilityRestJobs started in n.nnn seconds.
    ```

    You can also call z/OSMF RESTJOBS APIs directly from your Internet browser with a URL, for example,

    https://your.server:securezosmfport/zosmf/restjobs/jobs

    where the *securezosmfport* is 443 by default. You can verify the port number by checking the *izu.https.port* variable assignment in the z/OSMF `bootstrap.properties` file.

    You might get error message IZUG846W, which indicates that a cross-site request forgery (CSRF) was attempted. To resolve the issue, update your browser by adding the `X-CSRF-ZOSMF-HEADER` HTTP custom header to every cross-site request. This header can be set to any value or an empty string (""). For details, see the z/OSMF documentation. If calling the z/OSMF RESTJOBS API directly fails, fix z/OSMF before explorer server can use these APIs successfully. 

-   If testing the explorer server REST API for data set information fails, check the z/OSMF IZUSVR1 task output for errors and confirm that the z/OSMF RESTFILES services are started successfully. If no errors occur, you can see the following message in the IZUSVR1 job output:

    ```
    CWWKZ0001I: Application IzuManagementFacilityRestFiles started in n.nnn seconds.
    ```

    You can also call z/OSMF RESTFILES APIs directly from your internet browser with a URL, for example,

    https://your.server:securezosmfport/zosmf/restfiles/ds?dslevel=userid.**

    where the *securezosmfport* is 443 by default. You can verify the port number by checking the *izu.https.port* variable assignment in the z/OSMF `bootstrap.properties` file.

    You might get error message IZUG846W, which indicates that a cross-site request forgery (CSRF) was attempted. To resolve the issue, update your browser by adding the `X-CSRF-ZOSMF-HEADER` HTTP custom header to every cross-site request. This header can be set to any value or an empty string (""). For details, see the z/OSMF documentation. If calling the z/OSMF RESTFILES API directly fails, fix z/OSMF before explorer server can use these APIs successfully.

    **Tip:** The z/OSMF installation step of creating a valid IZUFPROC procedure in your system PROCLIB might be missed. For more information, see the *z/OSMF Configuration Guide*.

    The IZUFPROC member resides in your system PROCLIB, which is similar to the following sample:

    ```
    //IZUFPROC PROC ROOT='/usr/lpp/zosmf'  /* zOSMF INSTALL ROOT     */
    //IZUFPROC EXEC PGM=IKJEFT01,DYNAMNBR=200                          
    //SYSEXEC  DD DISP=SHR,DSN=ISP.SISPEXEC                            
    //         DD DISP=SHR,DSN=SYS1.SBPXEXEC                           
    //SYSPROC  DD DISP=SHR,DSN=ISP.SISPCLIB                            
    //         DD DISP=SHR,DSN=SYS1.SBPXEXEC                           
    //ISPLLIB  DD DISP=SHR,DSN=SYS1.SIEALNKE                           
    //ISPPLIB  DD DISP=SHR,DSN=ISP.SISPPENU                            
    //ISPTLIB  DD RECFM=FB,LRECL=80,SPACE=(TRK,(1,0,1))                
    //         DD DISP=SHR,DSN=ISP.SISPTENU                            
    //ISPSLIB  DD DISP=SHR,DSN=ISP.SISPSENU                            
    //ISPMLIB  DD DISP=SHR,DSN=ISP.SISPMENU                            
    //ISPPROF  DD DISP=NEW,UNIT=SYSDA,SPACE=(TRK,(15,15,5)),            
    //         DCB=(RECFM=FB,LRECL=80,BLKSIZE=3120)                     
    //IZUSRVMP DD PATH='&ROOT./defaults/izurf.tsoservlet.mapping.json'  
    //SYSOUT   DD SYSOUT=H                                              
    //CEEDUMP  DD SYSOUT=H                                              
    //SYSUDUMP DD SYSOUT=H                                              
    //                                                                 
    ```

    **Note:** You might need to change paths and data sets names to match your installation.

    A known issue and workaround for RESTFILES API can be found at [TSO SERVLET EXCEPTION ATTEMPTING TO USE RESTFILE INTERFACE](http://www-01.ibm.com/support/docview.wss?crawler=1&uid=isg1PI63398).

-   Check your system console log for related error messages and respond to them.

If the explorer server cannot connect to the z/OSMF server, check the following item:

By default, the explorer server communicates with the z/OSMF server on the localhost address. If your z/OSMF server is on a different IP address to the explorer server, for example, if you are running z/OSMF with Dynamic Virtual IP Addressing (DVIPA), you can change this by adding a `ZOSMF_HOST` parameter to the server.env file. For example: `ZOSMF_HOST=winmvs27`.
