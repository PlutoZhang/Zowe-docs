<div id="page">

<div id="main" class="aui-page-panel">

<div class="aui-page-panel-nav">

<div class="aui-navgroup-inner">

<div id="tabs-nav" class="aui-tabs horizontal-tabs">

  - [**Contents**](#tabs-navigation)
  - [**Search**](#tabs-search)

<div id="tabs-navigation" class="tabs-pane active-pane" data-current-page-id="433363265">

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
3.  <span> [Overview of the z/OS Management Facility Configuration
    Process](433363261.html)
</span>

</div>

# <span id="title-text"> Brightside CLI : Configure z/OS Management Facility Cloud Provisioning Security </span>

</div>

<div id="content" class="view">

<div class="page-metadata">

</div>

<div id="main-content" class="wiki-content group">

As a security administrator, complete the z/OSMF cloud provisioning
security configuration tasks for your Brightside
CLI implementation.

<div class="confluence-information-macro confluence-information-macro-warning">

<span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Important\!** The [IBM z/OS Management
Facility](https://www.ibm.com/support/knowledgecenter/en/SSLTBW_2.2.0/com.ibm.zos.v2r2.izu/izu.htm)
guide on the IBM Knowledge Center is your primary source of information
about how to install and configure z/OSMF. Throughout the IBM
procedures, we provide Brightside CLI-specific tips or<span>
requirements. We recommend that you open IBM documentation in a separate
browser tab.</span>

</div>

</div>

## Configure z/OSMF Cloud Provisioning to Use RACF Security

For RACF installations, IBM provides security commands
in `SYS1.SAMPLIB` for Cloud provisioning. If you do not
see RACF commands for Cloud Provisioning in member `IZUSEC`, you might
need to apply various APAR or PTFs or upgrade your current level of
z/OSMF.

  - [Required APARs and
    PTFs](#Configurez/OSManagementFacilityCloudProvisioningSecurity-RequiredAPARsandPTFs)
  - [How the RACF Security REXX EXEC Workflow
    Works](#Configurez/OSManagementFacilityCloudProvisioningSecurity-HowtheRACFSecurityREXXEXECWorkflowWorks)
  - [Security Groups Naming
    Conventions](#Configurez/OSManagementFacilityCloudProvisioningSecurity-SecurityGroupsNamingConventions)
  - [ZMFCLOUD Class Resource Profiles for Cloud
    Provisioning](#Configurez/OSManagementFacilityCloudProvisioningSecurity-ZMFCLOUDClassResourceProfilesforCloudProvisioning)
  - [Restrict Access to z/OS UNIX File
    Systems](#Configurez/OSManagementFacilityCloudProvisioningSecurity-RestrictAccesstoz/OSUNIXFileSystems)

<div class="confluence-information-macro confluence-information-macro-information">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information about configuring z/OSMF cloud
provisioning using RACF, see [Security configuration requirements for
z/OSMF](https://www.ibm.com/support/knowledgecenter/en/SSLTBW_2.2.0/com.ibm.zos.v2r2.izua300/izuconfig_SecurityStructuresForZosmf.htm)
on the IBM Knowledge Center.

</div>

</div>

### Required APARs and PTFs

For z/OS V2R2, our installation requires the following IBM z/OS APARs
and PTFs:

`PI70526 / UI42847`

`PI67837 / UI42849`

`PI73643 / UI43848`

`PI77710 / UI46267`

`PI77388 / UI46543 (`Manual security mode for a domain)

### How the RACF Security REXX Exec Workflow Works

The RACF REXX exec workflow creates multiple domain-specific user groups
and issues commands that permit the user groups to access protected
class resources that are also domain-specific. 

You can find the RACF Security REXX exec workflow in the following file:

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
/var/zosmf/configuration/workflow/izu.provisioning.security.config.rexx
```

</div>

</div>

The REXX exec workflow creates and maintains the following user groups:

  - **Domain Landlords**  
    Define cloud domains and their associated resources. Designates
    domain administrators.
  - **Domain Administrators**  
    Manage domains, define, and manage the relationships for and between
    domain services, tenants, and resource pools.
  - **Resource Pool WLM Resource Pool Administrators**  
    Manage networking and workload management (WLM) resources in clouds.
  - **Consumers**  
    Access the software services and resource pools for
tenants.

<div class="confluence-information-macro confluence-information-macro-warning">

<span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Important\!** When Landlords or Domain Administrators create or modify
domains, the RACF Security REXX exec workflow is submitted under the
user ID that was designated as the security administrator for the
domain. The workflows behave in this manner even when the domain
security administrator is (or is not) logged in as the user that is
creating or modifying the domain. Although landlords or domain
administrators might not possess the RACF SPECIAL attribute, they can
submit security workflows under a USERID of someone that possesses the
RACF SPECIAL attribute. However, there is a security exposure when you
use this approach.

  - As a USS file, the Security REXX exec can be modified by anyone that
    has write access, which includes super users, but not necessarily
    security administrators.

IBM's response to this exposure is as follows:

  - After security administrators define the resources and activate the
    FSACCESS class, the z/OSMF data file system is protected. Only the
    users that are permitted to this access the resource can update
    them. Therefore, UID(0) cannot manipulate z/OSMF files unless they
    are explicitly authorized to do
    so.<span style="color: rgb(0,0,0);"> </span>IZUSVR (the user ID of
    the z/OSMF started task server) and IZUSECAD (the z/OSMF security
    admin group) need to be granted with UPDATE access to this resource.

For more information, see [OA35970: NEW FUNCTION - NEW ACCESS CONTROL
CHECK USING FSACCESS CLASS PROFILE. SEE ALSO OA35973 AND
OA35974](http://www-01.ibm.com/support/docview.wss?uid=isg1OA35970) on
the IBM Support website.

</div>

</div>

### Security Groups Naming Conventions

By default, the name of the security user group that contains Domain
Landlords is **`IYU`**. The Domain Landlord user group name is also used
by z/OSMF as a prefix to all the security user groups for a domain when
a domain is created.

The name of the Landlord user group should be the same as the name that
is identified to z/OSMF in your system `PARMLIB IZUPRMxx` member, for
parameter `CLOUD_SAF_PREFIX`.  By default, `CLOUD_SAF_PREFIX('IYU')`.

Only the user IDs that are members of the Domain Landlord group and in
the Administrator group for the domain can see the **Resource
Management** and **Software Services** options the **Cloud
Provisioning** section of the IBM z/OS Management Facility navigation
tree.

<span class="confluence-embedded-file-wrapper confluence-embedded-manual-size">![](attachments/433363265/433363266.png)</span>

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** Both of the Cloud Provisioning options are ***not required***
to provision.

</div>

</div>

As a Landlord, each domain that you create is associated with a Domain
ID. The Domain ID is assigned during the process of creating the
domain and cannot be modified. The process uses
the `CLOUD_SAF_PREFIX` value followed by a number to create the Domain
ID.

The naming convention for security user groups in a Domain is the Domain
ID followed by a group identifier. For example, `(0, RPAN,RPAW,00). T`he
following example illustrates the naming convention for security user
groups in a Domain: 

  - **Default Domain ID:** `IYU0`  
    **Example: **The CLOUD\_SAF\_PREFIX, is IYU plus the number `0`
  - **Domain Administrators user group:** `IYU0`
  - **Network Resource Pool Administrators user group:** `IYU0RPAN`
  - **WLM Resource Pool Administrators user group:** `IYU0RPAW`
  - **Tenant consumers of the domain resources user group:** `IYU000`

### ZMFCLOUD Class Resource Profiles for Cloud Provisioning

<span>Cloud provisioning for z/OSMF requires the following profiles and
user groups:</span>

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
IZUDFLT.ZOSMF.PROVISIONING.RESOURCE_MANAGEMENT.
IYU IYU
```

</div>

</div>

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
IZUDFLT.ZOSMF.SECURITY.ADMIN
IZUSECAD
```

</div>

</div>

You can find the provisioning RACF Security REXX exec Workflow that IBM
provides in the following file:

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
/var/zosmf/configuration/workflow/izu.provisioning.security.config.rexx
```

</div>

</div>

The Landlord that created the Domain submits the REXX exec workflow
under the user ID that was specified as the Domain Security
Administrator. To execute the Security REXX exec Workflow successfully,
the Domain Security Administrator's user ID must be associated with the
RACF SPECIAL attribute, and connected to the IZUSECAD user group.

### Restrict Access to z/OS UNIX File Systems

Security administrators can use RACF to provide and maintain data and
system security to z/OS UNIX file
systems.

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** For more information, see [Using the FSACCESS class profile to
restrict
access](https://www.ibm.com/support/knowledgecenter/en/SSLTBW_2.2.0/com.ibm.zos.v2r2.bpxb200/fsastepp.htm)
on the IBM Knowledge
Center.

</div>

</div>

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

<span style="color: rgb(0,0,0);"><span style="color: rgb(0,0,0);"><span style="color: rgb(0,0,0);"><span style="color: rgb(0,0,0);">**Note:**
When the FSACCESS class profile is active,
RACF </span><span style="color: rgb(0,0,0);">uses the FSACCESS class
profile resources to
determine </span><span style="color: rgb(0,0,0);">whether the user is
authorized to access the file system.
When </span></span></span></span><span style="color: rgb(0,0,0);">the
user is authorized to access the file system
resource, </span><span style="color: rgb(0,0,0);">RACF uses the
permission bits, Access Control Lists (ACLs), and
various </span><span style="color: rgb(0,0,0);">UNIXPRIV class profiles
to determine if the user
is </span><span style="color: rgb(0,0,0);">authorized to access the
individual file system objects
with </span><span style="color: rgb(0,0,0);">the requested access
level.</span>

</div>

</div>

The provisioning RACF Security REXX exec Workflow establishes the
following profiles, user groups, and permissions during the process of
creating a domain: 

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
IZUDFLT.ZOSMF.PROVISIONING.RESOURCE_MANAGEMENT.IYUx
IYU (Permit Only)
IYUx
```

</div>

</div>

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
IZUDFLT.ZOSMF.RESOURCE_POOL.NETWORK.IYUx
IYUxRPAN
```

</div>

</div>

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
IZUDFLT.ZOSMF.RESOURCE_POOL.WLM.IYUx
IYUxRPAW
```

</div>

</div>

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
IZUDFLT.ZOSMF.TEMPLATE.APPROVERS.IYUx
Individual user access
```

</div>

</div>

The process of creating templates and template instances (where the
domain ID is `IYUx`) establishes the following profiles and user groups:

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
IZUDFLT.ZOSMF.TEMPLATE.APPROVERS.IYUx.templatename
Individual user access or user groups
```

</div>

</div>

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
IZUDFLT.ZOSMF.TEMPLATE.INSTANCE.IYUx.templatename_instancename
IYUx00
```

</div>

</div>

The process of creating tenants (where the domain ID is `IYUx`)
establishes the following profiles and user groups: 

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
IZUDFLT.ZOSMF.PROVISIONING.RESOURCE_MANAGEMENT.IYUx00
IYUx00
```

</div>

</div>

## Next Steps

After you complete the security administration for z/OSMF and cloud
provisioning, systems programmers, security administrators, and
application developers can issue the validate profile command. The
command tests the end-to-end solution to verify that Brightside CLI can
communicate with z/OS systems properly. For more information,
see [Identify and Correct Problems Detected by the Validate Profile
Command](Identify-and-Correct-Problems-Detected-by-the-Validate-Profile-Command_433363269.html). 

Work with a systems programmer to correct any problems in the profile
validation report. When all tests receive an *OK* result, application
developers can install Brightside CLI and issue commands on z/OS
systems.

 

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
