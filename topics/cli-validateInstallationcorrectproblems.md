# Correcting problems detected by the validate profile command in Brightside CLI

Brightside CLI includes a profile validation command that runs a series
of tests on z/OSMF REST APIs (and their endpoints) and prints a report
that can help you identify problems with profiles and connection
details. As a systems programmer, issue this command to test the
end-to-end integration of Brightside CLI with your z/OSMF and your z/OS
environment. 

**Note:** Application developers that use Brightside CLI can issue the
command at any time and provide the report to systems programmers for
problem resolution. For more information about how application
developers use the profile validation command, see [Validate Installation](./cli-validateInstallation.md). 

## Run tests on z/OSMF REST APIs and generate a report

After you configure z/OSMF, install the z/OSMF plugins, and configure
security, you can install Brightside CLI and issue the profile
validation commands to test the configuration.

**Follow these steps:**

1.  Install Brightside CLI on your personal computer. For detailed
    instructions, see [Install Brightside CLI](./cli-installcli.md).
2.  (Optional) You might want to issue the `bright zosmf validate
    profile --print-plan-only` command to see a list of REST endpoints
    that Brightside CLI will test.
3.  Issue the `bright zosmf validate profile` command to run the
    tests.  
    Brightside CLI generates a report that shows if each test was
    successful. You can use the report to resolve problems in your
    configuration. 

## Use the report to resolve problems

You can use the results of the validate profile command to troubleshoot
and fix problems with your z/OSMF configuration. The result of each test
returns as *OK*, *Warning*, or *Failed*. If you receive a *Warning* or
*Failed* result on a test, you can refer to IBM documentation for
information on how to configure that particular REST API. For
information on which of the z/OSMF REST APIs Brightside CLI uses,
see [Configure z/OS Management Facility Security](./cli-configzosmfsecurity.md). We provide links to IBM documentation for configuring each REST API. 

For example, you receive a *Failed* result on the "Issue Console
command" task. Refer to the list of REST APIs in [Configure z/OS Management Facility Security](./cli-configzosmfsecurity.md) and follow the links to
the corresponding IBM documentation for the z/OS console services API. 

The following is an example of the output from the` `<span>`bright zosmf
validate profile --print-plan-only`
command:</span>

``` 
╔═════════════════════╤══════════════════════════╤══════════════════════════════════════╗
║Task                 │Description               │Endpoints                             ║
╟─────────────────────┼──────────────────────────┼──────────────────────────────────────╢
║Get z/OSMF info      │Retrieving basic info     │GET /zosmf/info                       ║
║                     │about your instance of    │                                      ║
║                     │z/OSMF such as host name, │                                      ║
║                     │port, version, etc.       │                                      ║
╟─────────────────────┼──────────────────────────┼──────────────────────────────────────╢
║Issue TSO command    │Issuing the TSO command   │POST /zosmf/tsoApp, PUT               ║
║                     │'status' to test TSO API  │/zosmf/tsoApp, GET                    ║
║                     │access. Creates a TSO     │/zosmf/tsoApp, DELETE                 ║
║                     │address space, sends a    │/zosmf/tsoApp                         ║
║                     │message to it, and checks │                                      ║
║                     │the output                │                                      ║
╟─────────────────────┼──────────────────────────┼──────────────────────────────────────╢
║Issue Console command│Issuing the console       │PUT                                   ║
║                     │command 'd iplinfo' to    │/zosmf/restconsoles/defcn             ║
║                     │test Console API access.  │                                      ║
║                     │'d iplinfo' is a simple   │                                      ║
║                     │console command to print  │                                      ║
║                     │the last time the z/OS    │                                      ║
║                     │system was booted.        │                                      ║
╟─────────────────────┼──────────────────────────┼──────────────────────────────────────╢
║Submit a job         │Submit an IEFBR14 job     │PUT /zosmf/restjobs/jobs              ║
║                     │using the z/OSMF jobs API │                                      ║
╟─────────────────────┼──────────────────────────┼──────────────────────────────────────╢
║Get job status       │Get the status of the     │GET                                   ║
║                     │submitted job and ensure  │/zosmf/restjobs/jobs/<jobname>/<jobid>║
║                     │its completion code is 0  │                                      ║
╟─────────────────────┼──────────────────────────┼──────────────────────────────────────╢
║Delete/purge a job   │Delete the submitted job, │DELETE                                ║
║                     │purging its output from   │/zosmf/restjobs/jobs/<jobname>/<jobid>║
║                     │the spool.                │                                      ║
╟─────────────────────┼──────────────────────────┼──────────────────────────────────────╢
║Create a data set    │Create a data set with a  │PUT                                   ║
║                     │random data set name      │/zosmf/restfiles/ds/<dsname>          ║
╟─────────────────────┼──────────────────────────┼──────────────────────────────────────╢
║Write to a data set  │Write to the created data │PUT                                   ║
║                     │set                       │/zosmf/restfiles/ds/<dsname>          ║
╟─────────────────────┼──────────────────────────┼──────────────────────────────────────╢
║Read from a data set │Read from the created data│GET                                   ║
║                     │set                       │/zosmf/restfiles/ds/<dsname>          ║
╟─────────────────────┼──────────────────────────┼──────────────────────────────────────╢
║Delete a data set    │Delete the created data   │DELETE                                ║
║                     │set                       │/zosmf/restfiles/ds/<dsname>          ║
╚═════════════════════╧══════════════════════════╧══════════════════════════════════════╝
```

