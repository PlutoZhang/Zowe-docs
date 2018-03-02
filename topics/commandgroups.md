<div id="page">

<div id="main" class="aui-page-panel">

<div class="aui-page-panel-nav">

<div class="aui-navgroup-inner">

<div id="tabs-nav" class="aui-tabs horizontal-tabs">

  - [**Contents**](#tabs-navigation)
  - [**Search**](#tabs-search)

<div id="tabs-navigation" class="tabs-pane active-pane" data-current-page-id="447395688">

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

# <span id="title-text"> Brightside CLI : Brightside CLI Command Groups </span>

</div>

<div id="content" class="view">

<div class="page-metadata">

</div>

<div id="main-content" class="wiki-content group">

Brightside CLI contains command groups that focus on specific business
processes that you (application developers and systems programmers)
perform during your day-to-day activities. For example, the compiler
command group lets you perform tasks that relate to compiling source
code on mainframe systems. The projects command group lets you perform
tasks that relate to managing source code that you store in version
control systems, such as Git and CA Endevor. You can perform all the
tasks that relate to these business processes using a unified
command-line interface - Brightside CLI.

The command groups contain commands that let you perform actions on
specific objects. For each action on an object, you can specify options
that you apply as the Brightside CLI commands execute.

In this article, we review all the Brightside CLI command groups and
provide you with a brief synopsis of the tasks that you can perform
using the commands in each group. For more information, see [How to
Display Brightside CLI
Help](How-to-Display-Brightside-CLI-Help_429365003.html). 

<div class="confluence-information-macro confluence-information-macro-warning">

<span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Important\!** Before you issue these commands, ensure that you create
and [validate your zosmf profile](Validate-Installation_430335233.html)
so that Brightside CLI can communicate with z/OS systems.

</div>

</div>

  
Brightside CLI contains the following command groups:

<div class="toc-macro rbtoc1519943048671">

  - [ca-disk](#BrightsideCLICommandGroups-ca-disk)
  - [cics](#BrightsideCLICommandGroups-cics)
  - [compiler](#BrightsideCLICommandGroups-compiler)
  - [config](#BrightsideCLICommandGroups-config)
  - [contribute](#BrightsideCLICommandGroups-contribute)
  - [db2](#BrightsideCLICommandGroups-db2)
  - [endevor ](#BrightsideCLICommandGroups-endevor)
  - [help](#BrightsideCLICommandGroups-help)
  - [ipcs](#BrightsideCLICommandGroups-ipcs)
  - [profiles](#BrightsideCLICommandGroups-profiles)
  - [projects](#BrightsideCLICommandGroups-projects)
  - [provisioning](#BrightsideCLICommandGroups-provisioning)
  - [zos-console](#BrightsideCLICommandGroups-zos-console)
  - [zos-files](#BrightsideCLICommandGroups-zos-files)
  - [zos-jobs](#BrightsideCLICommandGroups-zos-jobs)
  - [zos-ssh](#BrightsideCLICommandGroups-zos-ssh)
  - [zos-tso](#BrightsideCLICommandGroups-zos-tso)
  - [zos-utils](#BrightsideCLICommandGroups-zos-utils)
  - [zosmf](#BrightsideCLICommandGroups-zosmf)

</div>

## ca-disk

The ca-disk command group is an [experimental command
group](Enable-and-Disable-Experimental-Commands_433363274.html) that
lets you interact with [CA Disk Backup and
Restore](https://docops.ca.com/ca-disk-backup-and-restore/12-5/en) from
a familiar command-line interface. To execute commands using the ca-disk
command group, [CA Disk Backup and
Restore](https://support.ca.com/cadocs/0/CA%20Disk%20%20Backup%20and%20Restore%2012%205-ENU/Bookshelf.html)
must be installed on your system.

With the ca-disk command group, you can perform the following tasks:

  - Archive and restore data sets that you archived using [CA Disk
    Backup and
    Restore](https://docops.ca.com/ca-disk-backup-and-restore/12-5/en).

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information about ca-disk syntax, actions, and
options, open Brightside CLI, and issue the following command:

`bright ca-disk -h`

</div>

</div>

## cics

The cics command group is an [experimental command
group](Enable-and-Disable-Experimental-Commands_433363274.html) that
lets you interact with CICS regions from a familiar command-line
interface. 

With the cics command group, you can perform the following tasks:

  - Start or stop a CICS region.
  - Manage CICS resources such as DB2CONN, MQCONN, PROGRAM, and
    TRANSACTION.
  - Issue MVS modify commands against a CICS region.
  - Run a CICS 3270 MQ Bridge transaction. 
  - Submit batch utilities such as
DFHCSDUP.

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information about cics syntax, actions, and options,
open Brightside CLI, and issue the following command:

`bright cics -h`

</div>

</div>

## compiler

The compiler command group is an [experimental command
group](Enable-and-Disable-Experimental-Commands_433363274.html) that
lets you compile code on mainframe systems. As a developer, you can use
Brightside CLI to work on mainframe code locally and compile the code.

With the compiler command group, you can perform the following tasks:

  - Build and compile COBOL (common business-oriented language) and
    HLASM (IBM High Level Assembler) source code on mainframe
systems.

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information about compiler syntax, actions, and
options, open Brightside CLI, and issue the following command:

`bright compiler -h`

</div>

</div>

## config

The config command group lets you display and configure Brightside
CLI settings and values to fit your needs. 

With the config command group, you can perform the following tasks:

  - Display the location of the Brightside CLI configuration directory
    on your PC
  - Display the status of experimental features and commands (enabled or
    disabled).
  - Enable and disable experimental features and
commands.

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information about config syntax, actions, and
options, open Brightside CLI, and issue the following command:

`bright config -h`

</div>

</div>

## contribute

The contribute command group lets you generate code that you can
contribute to help improve Brightside CLI.

With the contribute command group, you can perform the following tasks:

  - Submit feedback to the Brightside CLI engineering
team.

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information about contribute syntax, actions, and
options, open Brightside CLI, and issue the following command:

`bright contribute -h`

</div>

</div>

## db2

The db2 command group is an [experimental command
group](Enable-and-Disable-Experimental-Commands_433363274.html) that
lets you interact with the IBM Db2 Databases.

To execute commands in the db2 command group, IBM Db2 Database must be
installed and configured on your system. With the db2 command group, you
can perform the following tasks:

  - Submit batch jobs to execute Db2 SQL and interact with databases.
  - Export Db2 tables to stdout or a local file on your PC. 
  - Create and manage Db2 profiles that allow you to target specific Db2
    regions, libraries, and plan names. To use Db2 commands, you must
    also specify a basic zosmf
profile. 

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information about db2 syntax, actions, and options,
open Brightside CLI, and issue the following command:

`bright db2 -h`

</div>

</div>

## endevor 

The endevor command group is an [experimental command
group](Enable-and-Disable-Experimental-Commands_433363274.html) that
lets you interact with CA Endevor remotely.

To execute commands in the endevor command group, CA Endevor must be
installed and configured on your system. With the endevor command group,
you can perform the following tasks:

  - Submit Software Control Language (SCL) to CA Endevor SCM to manage
    elements, packages, symbols, systems, and more. To learn more about
    the flexibility of SCL, see the IBM SCL Reference Guide. 
  - Generate, delete, and move CA Endevor
elements.

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information about endevor syntax, actions, and
options, open Brightside CLI, and issue the following command:

`bright endevor -h`

</div>

</div>

## help

The help command group provides context-sensitive help in Brightside
CLI.

With the help command group, you can perform the following tasks:

  - Get general information about Brightside CLI and learn how to create
    profiles and job cards. 
  - Get context-sensitive help for any command, action, object, and
    option.
  - Learn about common mainframe terms and concepts. For example, you
    can display a description of how data set naming conventions work on
    z/OS.
  - Search all Brightside CLI help text for a specific term or
phrase.

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information, see [How to Display Brightside CLI
Help](How-to-Display-Brightside-CLI-Help_429365003.html).

</div>

</div>

## ipcs

The ipcs command group is an [experimental command
group](Enable-and-Disable-Experimental-Commands_433363274.html) that
lets you interact with Interactive Problem Control System (IPCS) on
z/OS. With the ipcs command group, you can perform the following tasks:

  - Submit a command to IPCS and review the dump data in a data set of
    your choice. 
  - Parse the IPCS dump data with a JSON options document to isolate
    specific
data.

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information about ipcs syntax, actions, and options,
open Brightside CLI, and issue the following command:

`bright ipcs -h`

</div>

</div>

## profiles

The projects command group is an [experimental command
group](Enable-and-Disable-Experimental-Commands_433363274.html) that
lets you create, manage, and validate profiles for use with other
Brightside CLI command groups. Profiles allow you to issue commands to
different systems quickly, without specifying your connection details
with every command.

With the profiles command group, you can perform the following tasks:

  - Create, update, and delete profiles for anyBrightside CLI command
    group that supports profiles. 
  - Set the default profile to be used within any Brightside CLI command
    group.
  - List profile names and details for any Brightside CLI command group,
    including the default active profile.
  - Validate profiles for other Brightside CLI command groups. For more
    information, see [Validate
    Installation](Validate-Installation_430335233.html).

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For general information about profiles, open Brightside CLI,
and issue the following command:

`bright help explain profiles`<span> </span>

For more information about profiles syntax, actions, and options, open
Brightside CLI, and issue the following commands:

`bright profiles -h`

</div>

</div>

## projects

The projects command group is an [experimental command
group](Enable-and-Disable-Experimental-Commands_433363274.html) that
lets you interact with projects in CA Endevor, Git, or other version
control software. If you use Git, a minimum of Git version 2.9 is
required.

With the projects command group, you can perform the following tasks:

  - Generate an element from your CA Endevor project.
  - Create/initialize a new project (CA Endevor, Git, Mercurial, or data
    set) from mainframe source code. 
  - Generate a list of all files that are tracked by the current
    project.
  - Pull changes from version control software of your choice, or
    retrieve element listings from CA Endevor. 
  - Synchronize element listings and upload elements to your
project.

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information about projects syntax, actions, and
options, open Brightside CLI, and issue the following command:

`bright projects -h`

</div>

</div>

## provisioning

The provisioning command group lets you perform IBM z/OSMF provisioning
tasks with templates and provisioned instances from Brightside CLI.

With the provisioning command group, you can perform the following
tasks:

  - Provision cloud instances using z/OSMF Software Services templates.
  - List information about the available z/OSMF Service Catalog
    published templates and the templates that you used to publish cloud
    instances.
  - List summary information about the templates that you used to
    provision cloud instances. You can filter the information by
    application (for example, DB2 and CICS) and by the external name of
    the provisioned instances.
  - List detail information about the variables used (and their
    corresponding values) on named, published cloud
instances.

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information about provisioning syntax, actions, and
options, open Brightside CLI, and issue the following command:

`bright provisioning -h`

</div>

</div>

## zos-console

The zos-console command group lets you issue commands to the z/OS
console by establishing an extended Multiple Console Support (MCS)
console.

With the zos-console command group, you can perform the following
tasks:

<div class="confluence-information-macro confluence-information-macro-warning">

<span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Important\!**<span> Before you issue z/OS console commands with
Brightside CLI, security administrators should ensure that they provide
access to commands that are appropriate for your organization.</span>

</div>

</div>

  - Issue commands to the z/OS console.
  - Collect command responses and continue to collect solicited command
    responses
on-demand.

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information about zos-console syntax, actions, and
options, open Brightside CLI, and issue the following command:

`bright zos-console -h`

</div>

</div>

## zos-files

The zos-files command group lets you interact with USS files and data
sets on z/OS systems.

With the zos-files command group, you can perform the following tasks:

  - Create partitioned data sets (PDS) with members, physical sequential
    data sets (PS), and other types of data sets from templates. You can
    specify options to customize the data sets you create.  
  - Edit data sets locally in your preferred Integrated Development
    Environment (IDE). Your changes are reflected on the mainframe when
    you save the local file.
  - Download data sets or USS files from a mainframe to your local PC. 
  - Upload local files to mainframe data sets.
  - Interact with VSAM data sets directly, or invoke Access Methods
    Services (IDCAMS) to work with VSAM data sets.
  - List data sets, print data sets, and search the contents of a data
    set. 

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information about zos-console syntax, actions, and
options, open Brightside CLI, and issue the following command:

`bright zos-files -h`

See [Submit a Job and Print Job
Output](Submit-a-Job-and-Print-Job-Output_441193420.html) for a use-case
that demonstrates some zos-files commands.

</div>

</div>

## zos-jobs

The zos-jobs command group lets you submit jobs and interact with jobs
on z/OS systems.

With the zos-jobs command group, you can perform the following tasks:

  - Submit jobs from JCL that resides on the mainframe or a local file.
  - Delete jobs.
  - Download job output to your PC. 
  - List jobs. You can view finished jobs, active jobs, jobs in INPUT
    status, or all jobs.
  - Print various information about jobs and spool, such as spool
    content, JCL, JES messages, and more.
  - Create zos-jobs profiles that store your configuration details so
    that you can quickly interact with jobs.  To use zos-jobs commands,
    you must also specify a basic zosmf
profile. 

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information about zos-jobs syntax, actions, and
options, open Brightside CLI, and issue the following command:

`bright zos-jobs -h`

See [Submit a Job and Print the Job
Output](Submit-a-Job-and-Print-Job-Output_441193420.html) for a use case
that demonstrates some zos-jobs commands.

</div>

</div>

## zos-ssh

The zos-ssh command group is an [experimental command
group](Enable-and-Disable-Experimental-Commands_433363274.html) that
lets you interact with UNIX System Services (USS) on z/OS systems.

With the zos-ssh command group, you can perform the following tasks:

  - Issue USS commands via SSH (secure
shell) protocol. 

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information about zos-ssh syntax, actions, and
options, open Brightside CLI and issue the following command:

`bright zos-ssh -h`

</div>

</div>

## zos-tso

The zos-tso command group lets you issue TSO commands and interact with
TSO address spaces on z/OS systems.

With the zos-tso command group, you can perform the following tasks:

  - Create a TSO address space and issue TSO commands to the address
    space.
  - Review TSO command response data in Brightside
CLI.

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information about zos-tso syntax, actions, and
options, open Brightside CLI, and issue the following command:

`bright zos-tso -h `

</div>

</div>

## zos-utils

The zos-utils command group is an [experimental command
group](Enable-and-Disable-Experimental-Commands_433363274.html) that
lets you use common mainframe utilities remotely.

With the zos-utils command group, you can perform the following tasks:

  - Transfer a file across systems with a File Transfer Protocol (FTP)
    command. 
  - Copy data between data sets with the IEBCOPY utility.
  - Overwrite content in a data set with the IMASZAP
utility.

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information about zos-utils syntax, actions, and
options, open Brightside CLI, and issue the following command:

`bright zos-utils -h `

</div>

</div>

## zosmf

The zosmf command group lets you work with Brightside CLI profiles and
get general information about z/OSMF.

With the zosmf command group, you can perform the following tasks:

  - Create and manage your Brightside CLI zosmf profiles. You must have
    at least one zosmf profile to issue most commands. Issue the `bright
    help explain profiles` command in Brightside CLI to learn more about
    using profiles.
  - Verify that your profiles are set up correctly to communicate with
    z/OSMF on your system. For more information, see [Validate
    Installation](Validate-Installation_430335233.html).
  - Get information about the current z/OSMF version, host, port, and
    plugins installed on your
system.

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information about zosmf syntax, actions, and options,
open Brightside CLI, and issue the following command:

`bright zosmf -h `

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
