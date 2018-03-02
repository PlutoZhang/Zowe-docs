<div id="page">

<div id="main" class="aui-page-panel">

<div class="aui-page-panel-nav">

<div class="aui-navgroup-inner">

<div id="tabs-nav" class="aui-tabs horizontal-tabs">

  - [**Contents**](#tabs-navigation)
  - [**Search**](#tabs-search)

<div id="tabs-navigation" class="tabs-pane active-pane" data-current-page-id="430335233">

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

</div>

# <span id="title-text"> Brightside CLI : Validate Installation </span>

</div>

<div id="content" class="view">

<div class="page-metadata">

</div>

<div id="main-content" class="wiki-content group">

<span>After the systems programmer configures z/OSMF and application
developers install Brightside CLI, issue the Brightside CLI profile
validation command to verify that your z/OSMF profile will function
properly. The Brightside CLI profile validation command runs a series of
tests on z/OSMF APIs and prints a report that can help you identify
problems with your profile and connection details. </span>

Use this command to verify that your Brightside CLI profile can
communicate with z/OSMF on z/OS systems. Review the report and inform
your systems programmer if there are any failures or warnings.

<span>Before you issue the z/OSMF profile validation command,
ensure that the following tasks are complete:</span>

  - Your systems programmer has configured z/OSMF.
  - Brightside CLI is installed.
  - You created at least one Brightside CLI<span> "zosmf" profile that
    lets you access z/OSMF functionality on z/OS systems.</span>

## Command Syntax

You issue the z/OSMF validate profile command to verify that
your Brightside CLI mainframe security access has been properly
configured and that your profile details are correct. With the command,
you can verify your default profile or any other specific profile.

 Issue the following command to view a list of the tests that the
profile validation command will run:

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
bright zosmf validate profile --print-plan-only
```

</div>

</div>

Issue the following command to verify that your *default* *profile* is
configured correctly:

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
bright zosmf validate profile
```

</div>

</div>

Issue the following command and specify a `profile_name` to verify that
*a specific profile* is configured correctly:**  
**

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
bright zosmf validate --bpn <profile_name>
```

</div>

</div>

## Profile Validation Results

When you issue the z/OSMF validate profile command, Brightside CLI runs
a series of tests. <span>The command presents you with a table that
displays the test results.</span> Review the table and report any
failures or warnings to your systems programmer.

The following information is returned in the report:

  - **Task**  
    The type of action that the test performs.
  - **Status**  
    The result of the test returns as *OK*, *Warning*, or *Failed*. In
    some cases, a *Failed* result on one test can result in a
    *Warning* result on the subsequent tests.
  - **Description**  
    Details about the execution and results of the test.
  - **Endpoint**  
    The REST API endpoint on which the test acted.

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
