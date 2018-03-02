<div id="page">

<div id="main" class="aui-page-panel">

<div class="aui-page-panel-nav">

<div class="aui-navgroup-inner">

<div id="tabs-nav" class="aui-tabs horizontal-tabs">

  - [**Contents**](#tabs-navigation)
  - [**Search**](#tabs-search)

<div id="tabs-navigation" class="tabs-pane active-pane" data-current-page-id="433363269">

</div>

<div id="tabs-search" class="tabs-pane">

</div>

</div>

</div>

</div>

<div class="section aui-page-panel-content">

<div id="main-header">

<div id="breadcrumb-section">

1.  <span> [Brightside CLI](index.html) </span>
2.  <span> [Installing](Installing_429364995.html) </span>
3.  <span> [Validate Installation](Validate-Installation_430335233.html)
    </span>

</div>

# <span id="title-text"> Brightside CLI : Identify and Correct Problems Detected by the Validate Profile Command </span>

</div>

<div id="content" class="view">

<div class="page-metadata">

</div>

<div id="main-content" class="wiki-content group">

Brightside CLI includes a profile validation command that runs a series
of tests on z/OSMF REST APIs (and their endpoints) and prints a report
that can help you identify problems with profiles and connection
details. As a systems programmer, issue this command to test the
end-to-end integration of Brightside CLI with your z/OSMF and your z/OS
environment. 

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** Application developers that use Brightside CLI can issue the
command at any time and provide the report to systems programmers for
problem resolution. For more information about how application
developers use the profile validation command, see [Validate
Installation](Validate-Installation_430335233.html). 

</div>

</div>

## Run Tests on z/OSMF REST APIs and Generate a Report

After you configure z/OSMF, install the z/OSMF plugins, and configure
security, you can install Brightside CLI and issue the profile
validation commands to test the configuration.

**Follow these steps: **

1.  Install Brightside CLI on your personal computer. For detailed
    instructions, see [Install Brightside
    CLI](Install-Brightside-CLI_429364999.html).
2.  (Optional) You might want to issue the `bright zosmf validate
    profile --print-plan-only` command to see a list of REST endpoints
    that Brightside CLI will test.
3.  Issue the `bright zosmf validate profile` command to run the
    tests.  
    Brightside CLI generates a report that shows if each test was
    successful. You can use the report to resolve problems in your
    configuration. 

## Use the Report to Resolve Problems

You can use the results of the validate profile command to troubleshoot
and fix problems with your z/OSMF configuration. The result of each test
returns as *OK*, *Warning*, or *Failed*. If you receive a *Warning* or
*Failed* result on a test, you can refer to IBM documentation for
information on how to configure that particular REST API. For
information on which of the z/OSMF REST APIs Brightside CLI uses,
see [Configure z/OS Management Facility Security](433363263.html). We
provide links to IBM documentation for configuring each REST API. 

For example, you receive a *Failed* result on the "Issue Console
command" task. Refer to the list of REST APIs in [Configure z/OS
Management Facility Security](433363263.html) and follow the links to
the corresponding IBM documentation for the z/OS console services API. 

The following is an example of the output from the` `<span>`bright zosmf
validate profile --print-plan-only`
command:</span>

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
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

</div>

</div>

</div>

</div>

</div>

</div>

  - <span id="n-417294290">[Brightside CLI](index.html)</span>
      - <span id="n-417294291">[Release
        Notes](Release-Notes_417294291.html)</span>
    <!-- end list -->
      - <span id="n-429364995">[Installing](Installing_429364995.html)</span>
          - <span id="n-433363261">[Overview of the z/OS Management
            Facility Configuration Process](433363261.html)</span>
              - <span id="n-433363262">[Configure z/OS Management
                Facility](433363262.html)</span>
            <!-- end list -->
              - <span id="n-433363263">[Configure z/OS Management
                Facility Security](433363263.html)</span>
            <!-- end list -->
              - <span id="n-433363264">[Configure z/OS Management
                Facility Cloud Provisioning](433363264.html)</span>
            <!-- end list -->
              - <span id="n-433363265">[Configure z/OS Management
                Facility Cloud Provisioning
                Security](433363265.html)</span>
        <!-- end list -->
          - <span id="n-429364999">[Install Brightside
            CLI](Install-Brightside-CLI_429364999.html)</span>
        <!-- end list -->
          - <span id="n-430335233">[Validate
            Installation](Validate-Installation_430335233.html)</span>
              - <span id="n-433363269">[Identify and Correct Problems
                Detected by the Validate Profile
                Command](Identify-and-Correct-Problems-Detected-by-the-Validate-Profile-Command_433363269.html)</span>
    <!-- end list -->
      - <span id="n-429365002">[Using](Using_429365002.html)</span>
          - <span id="n-429365003">[How to Display Brightside CLI
            Help](How-to-Display-Brightside-CLI-Help_429365003.html)</span>
        <!-- end list -->
          - <span id="n-447395688">[Brightside CLI Command
            Groups](Brightside-CLI-Command-Groups_447395688.html)</span>
        <!-- end list -->
          - <span id="n-433363274">[Enable and Disable Experimental
            Commands](Enable-and-Disable-Experimental-Commands_433363274.html)</span>
        <!-- end list -->
          - <span id="n-441193419">[Brightside CLI
            Scenarios](Brightside-CLI-Scenarios_441193419.html)</span>
              - <span id="n-441193420">[Submit a Job and Print Job
                Output](Submit-a-Job-and-Print-Job-Output_441193420.html)</span>
    <!-- end list -->
      - <span id="n-38207496">[Legal
        Notices](Legal-Notices_38207496.html)</span>

<div id="footer">

<div class="section footer-body">

Copyright © 2018 CA. All rights reserved.

<div class="footer-logo">

</div>

Document generated on Mar 01, 2018 17:24.

</div>

</div>

</div>
