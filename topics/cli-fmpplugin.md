<div id="page">

<div id="main" class="aui-page-panel">

<div class="aui-page-panel-nav">

<div class="aui-navgroup-inner">

<div id="tabs-nav" class="aui-tabs horizontal-tabs">

  - [**Contents**](#tabs-navigation)
  - [**Search**](#tabs-search)

<div id="tabs-navigation" class="tabs-pane active-pane" data-current-page-id="475935701">

</div>

<div id="tabs-search" class="tabs-pane">

</div>

</div>

</div>

</div>

<div class="section aui-page-panel-content">

<div id="main-header">

<div id="breadcrumb-section">

1.  <span> [CA Brightside Community Edition](index.html) </span>
2.  <span> [Extending](Extending_475935698.html)
</span>

</div>

# <span id="title-text"> CA Brightside Community Edition : CA Brightside Plug-in for CA File Master Plus </span>

</div>

<div id="content" class="view">

<div class="page-metadata">

</div>

<div id="main-content" class="wiki-content group">

The CA Brightside plug-in for CA File Master Plus is a file management
and data manipulation tool. CA Brightside speeds up file creation and
manipulates virtual storage access method (VSAM), sequential and
partitioned data sets. CA Brightside also supports symbolic access to
data with layouts, and data manipulation such as selection of records in
data sets.

CA Brightside allows you to perform commands on multiple mainframe
applications at once from one command line window, without the need to
establish several mainframe sessions.

<div class="toc-macro rbtoc1528725936523">

  - [Plug-in
    Overview](#CABrightsidePlug-inforCAFileMasterPlus-Plug-inOverview)
  - [Use
    Cases](#CABrightsidePlug-inforCAFileMasterPlus-UseCases)
  - [Prerequisites](#CABrightsidePlug-inforCAFileMasterPlus-Prerequisites)
  - [Installation](#CABrightsidePlug-inforCAFileMasterPlus-Installation)
  - [Profile
    Setup](#CABrightsidePlug-inforCAFileMasterPlus-ProfileSetup)
  - [Commands](#CABrightsidePlug-inforCAFileMasterPlus-Commands)

</div>

## Plug-in Overview

Modern Application Developers / DevOps Admins script, using CLI, DevOps
processes that include VSAM file functions that enable Continuous
Testing. The file functions that CLI can invoke include copying,
renaming and deleting files, and populating files with data.

## Use Cases

As a developer or DevOps admin, you can use CA Brightside for CA File
Master Plus to:

  - Populate VSAM file A with newly constructed** **test data from the
    CLI interactively – **POPULATE**
  - Select desired parts of the source and copy only those parts over to
    a new VSAM file – **COPY **(WITH SELECTION CRITERIA)
  - Make an exact copy of VSAM file A using only one CLI command
    – **COPY**
  - Rename the VSAM file A and B with ARCHIVE as the second qualifier
    – **RENAME**
  - Delete VSAM file A using the CLI - **DELETE**

## Prerequisites

To use CA Brightside for CA File Master Plus, ensure that the CA File
Master Plus REST API is installed, configured, and
running.

<div class="confluence-information-macro confluence-information-macro-information">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**More information:**

  - [Installing the Eclipse User Interface and REST
    API](https://docops.ca.com/display/FMPLUS11/Installing+the+Eclipse+User+Interface+and+REST+API)
  - [Using the REST
    API](https://docops.ca.com/display/FMPLUS11/Using+the+REST+API)

</div>

</div>

## Installation

For information about how to install a plug-in to CA Brightside,
see [Install
Plug-ins](https://docops.ca.com/display/CMFAAS10/Install+Plug-ins).

## Profile Setup

Before you start to use CA Brightside for CA File Master Plus, complete
the following steps:

  - [Create a
    profile](#CABrightsidePlug-inforCAFileMasterPlus-CreateaProfile)
  - [Validate a
    profile](#CABrightsidePlug-inforCAFileMasterPlus-ValidateaProfile)

### Create a Profile

The `profiles create fmp `command lets you create a CA
Brightside profile for CA File Master
Plus.

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information about `profiles create fmp` syntax,
actions, and options, open CA Brightside, and issue the following
command:

`bright profiles create fmp -h`

</div>

</div>

### Validate a Profile

The `profiles validate fmp `command lets you validate a CA
Brightside profile.

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information about `profiles validate fmp` syntax,
actions, and options, open CA Brightside, and issue the following
command:

`bright profiles validate fmp -h`

</div>

</div>

## Commands

CA Brightside allows you to perform the following actions using File
Master Plus for MVS:

  - [Copy a data
    set](#CABrightsidePlug-inforCAFileMasterPlus-Copyadataset)
  - [Delete a data
    set](#CABrightsidePlug-inforCAFileMasterPlus-Deleteadataset)
  - [Populate a data set with
    data](#CABrightsidePlug-inforCAFileMasterPlus-Populateadatasetwithdata)
  - [Rename a data
    set](#CABrightsidePlug-inforCAFileMasterPlus-Renameadataset)

### Copy a Data Set

The `fmp copy ds` command lets you copy a data set with or without
applying layout or selection
criteria.

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information about `fmp copy ds` syntax, actions, and
options, open CA Brightside, and issue the following command:

`bright fmp copy ds -h`

</div>

</div>

### Delete a Data Set

The `fmp delete ds` command lets you delete a data
set.

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information about `fmp delete ds` syntax, actions,
and options, open CA Brightside, and issue the following command:

`bright fmp delete ds -h`

</div>

</div>

### Populate a Data Set with Data

The `fmp populate ds` command lets you populate a data set with
records.

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information about `fmp populate ds` syntax, actions,
and options, open CA Brightside, and issue the following command:

`bright fmp populate ds -h`

</div>

</div>

### Rename a Data Set

The `fmp rename ds` command lets you rename a data
set.

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information about `fmp rename ds` syntax, actions,
and options, open CA Brightside, and issue the following command:

`bright fmp rename ds -h`

<div>

`  `

</div>

</div>

</div>

</div>

</div>

</div>

</div>

  - <span id="n-473021279">[CA Brightside Community
    Edition](index.html)</span>
      - <span id="n-473021281">[Release
        Notes](Release-Notes_473021281.html)</span>
    <!-- end list -->
      - <span id="n-473021284">[Installing](Installing_473021284.html)</span>
          - <span id="n-473021285">[Prerequisites](Prerequisites_473021285.html)</span>
        <!-- end list -->
          - <span id="n-473021286">[z/OSMF Configuration
            Overview](473021286.html)</span>
              - <span id="n-473021287">[Configure
                z/OSMF](473021287.html)</span>
            <!-- end list -->
              - <span id="n-473021288">[Configure z/OSMF
                Security](473021288.html)</span>
        <!-- end list -->
          - <span id="n-473021289">[Install CA
            Brightside](Install-CA-Brightside_473021289.html)</span>
        <!-- end list -->
          - <span id="n-473021290">[Create a
            Profile](Create-a-Profile_473021290.html)</span>
        <!-- end list -->
          - <span id="n-473021291">[Test Connection to
            z/OSMF](473021291.html)</span>
        <!-- end list -->
          - <span id="n-473021293">[Uninstall CA
            Brightside](Uninstall-CA-Brightside_473021293.html)</span>
    <!-- end list -->
      - <span id="n-475935698">[Extending](Extending_475935698.html)</span>
          - <span id="n-473021292">[Install
            Plug-ins](Install-Plug-ins_473021292.html)</span>
        <!-- end list -->
          - <span id="n-475935700">[CA Brightside Plug-in for CA Endevor
            SCM](CA-Brightside-Plug-in-for-CA-Endevor-SCM_475935700.html)</span>
        <!-- end list -->
          - <span id="n-475935701">[CA Brightside Plug-in for CA File
            Master
            Plus](CA-Brightside-Plug-in-for-CA-File-Master-Plus_475935701.html)</span>
        <!-- end list -->
          - <span id="n-475943406">[CA Brightside Plug-in for IBM Db2
            Database](CA-Brightside-Plug-in-for-IBM-Db2-Database_475943406.html)</span>
    <!-- end list -->
      - <span id="n-473021294">[Using](Using_473021294.html)</span>
          - <span id="n-473021295">[Display
            Help](Display-Help_473021295.html)</span>
        <!-- end list -->
          - <span id="n-473021296">[Command
            Groups](Command-Groups_473021296.html)</span>
    <!-- end list -->
      - <span id="n-473021297">[Additional
        Resources](Additional-Resources_473021297.html)</span>
    <!-- end list -->
      - <span id="n-38207495">[Legal
        Notices](Legal-Notices_38207495.html)</span>

<div id="footer">

<div class="section footer-body">

Copyright © 2018 CA. All rights reserved.

<div class="footer-logo">

</div>

Document generated on Jun 11, 2018 10:05.

</div>

</div>

</div>
