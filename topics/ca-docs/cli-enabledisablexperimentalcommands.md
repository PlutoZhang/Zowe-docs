<div id="page">

<div id="main" class="aui-page-panel">

<div class="aui-page-panel-nav">

<div class="aui-navgroup-inner">

<div id="tabs-nav" class="aui-tabs horizontal-tabs">

  - [**Contents**](#tabs-navigation)
  - [**Search**](#tabs-search)

<div id="tabs-navigation" class="tabs-pane active-pane" data-current-page-id="433363274">

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
2.  <span> [Using](Using_429365002.html)
</span>

</div>

# <span id="title-text"> Brightside CLI : Enable and Disable Experimental Commands </span>

</div>

<div id="content" class="view">

<div class="page-metadata">

</div>

<div id="main-content" class="wiki-content group">

Brightside CLI includes experimental commands that are currently in
development and are not ready for general availability. You can enable
or disable these commands. The experimental commands are disabled by
default.

<div class="confluence-information-macro confluence-information-macro-warning">

<span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Important\!**  If you use these commands, you might encounter errors,
unexpected behavior, incompatibilities with your system, or incomplete
help text.

</div>

</div>

## Enable Experimental Commands

To enable the experimental commands, issue the following command:

`bright config set experimental-features enabled `

The experimental commands now appear in your help menu with the prefix
(*experimental)*.To view all available commands, including the
experimental commands, issue the following command: 

`bright -h`

## Disable Experimental Commands

To disable the experimental commands, issue the following command:

`bright config set experimental-features disabled `

## Check Status of Experimental Commands

To determine whether the experimental commands are enabled or disabled,
issue the following command:

`Bright config get
experimental-features`

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** Experimental commands display the prefix `(experimental)`
in Brightside CLI help when they are enabled. For
example:

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
cics               (experimental) Issue commands to interact with CICS regions 
compiler           (experimental) Compile source code on the mainframe
```

</div>

</div>

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
