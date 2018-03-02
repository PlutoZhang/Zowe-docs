<div id="page">

<div id="main" class="aui-page-panel">

<div class="aui-page-panel-nav">

<div class="aui-navgroup-inner">

<div id="tabs-nav" class="aui-tabs horizontal-tabs">

  - [**Contents**](#tabs-navigation)
  - [**Search**](#tabs-search)

<div id="tabs-navigation" class="tabs-pane active-pane" data-current-page-id="433363264">

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

# <span id="title-text"> Brightside CLI : Configure z/OS Management Facility Cloud Provisioning </span>

</div>

<div id="content" class="view">

<div class="page-metadata">

</div>

<div id="main-content" class="wiki-content group">

As a systems programmer, complete the following z/OSMF cloud
provisioning configurations tasks to supplement your Brightside
CLI implementation with z/OSMF cloud provisioning:

<div class="toc-macro rbtoc1519943043393">

  - [Install and Configure the IBM z/OS Provisioning
    Toolkit](#Configurez/OSManagementFacilityCloudProvisioning-InstallandConfiguretheIBMz/OSProvisioningToolkit)
  - [Configure z/OSMF Cloud
    Provisioning](#Configurez/OSManagementFacilityCloudProvisioning-Configurez/OSMFCloudProvisioning)
  - [Set Up the z/OSMF
    Cloud Provisioning Service](#Configurez/OSManagementFacilityCloudProvisioning-SetUpthez/OSMFCloudProvisioningService)
  - [Implement the z/OS Cloud Portal
    Plug-in](#Configurez/OSManagementFacilityCloudProvisioning-Implementthez/OSCloudPortalPlug-in)

</div>

<div class="confluence-information-macro confluence-information-macro-warning">

<span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Important\!** The [IBM z/OS Management
Facility](https://www.ibm.com/support/knowledgecenter/en/SSLTBW_2.2.0/com.ibm.zos.v2r2.izu/izu.htm)
guide on the IBM Knowledge Center is your primary source of information
about how to install and configure z/OSMF. Throughout the IBM
procedures, we provide Brightside CLI-specific tips or<span>
requirements. We recommend that you open IBM documentation in a separate
browser
tab.</span>

</div>

</div>

<div class="confluence-information-macro confluence-information-macro-tip">

<span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Tip:** Cloud provisioning is the process of providing resources to a
cloud provider's customers. With z/OSMF cloud provisioning enabled, you
can issue Brightside CLI commands to provision CICS, DB2, development
environments, and more. To learn more about z/OSMF and cloud
provisioning, see [What Cloud Provisioning
is](https://www.ibm.com/support/knowledgecenter/en/SSLTBW_2.2.0/com.ibm.zos.v2r2.izua300/izuconfig_CloudProvSecurityIntro.htm#SummaryCloudProvisioning)
on the IBM Knowledge Center.

</div>

</div>

For supplemental information about how security administrators configure
the security for z/OSMF cloud provisioning, see [Configure z/OSMF Cloud
Provisioning Security](433363265.html).

## Install and Configure the IBM z/OS Provisioning Toolkit

The [IBM® z/OS® Provisioning
Toolkit](https://developer.ibm.com/mainframe/products/zospt/) is a
command line utility that lets systems programmers and
application developers provision z/OS *development* environments. The
toolkit lets application developers with minimal z/OS specific
administration skills provision and deprovision z/OS applications
quickly. The toolkit also lets system programmers easily manage the
provisioning process by preconfiguring the environments, control
developer access through z/OS security, and set appropriate provisioning
limits.

IBM provides the z/OS Provisioning Toolkit with the following pax
file: `zospt_v#######.pax`. The toolkit runs on z/OS using UNIX System
Services (USS).

**Follow these steps:**

1.  [Install the
    toolkit](#Configurez/OSManagementFacilityCloudProvisioning-InstalltheToolkit).
2.  [Configure the z/OSMF properties file and
    templates](#Configurez/OSManagementFacilityCloudProvisioning-Configurethez/OSMFPropertiesFileandTemplates).

### Install the Toolkit

You acquire the z/OS Provisioning Toolkit installation files directly
from IBM. You must have an IBM account to download the files.

**Follow these steps:**

1.  Download the following IBM Provisioning Toolkit zip file
    from [IBM](https://developer.ibm.com/mainframe/products/zospt/) (log
    in required).
    
        zospt_vx.x.x.zip
    
    `vx.x.x` represents the current version level of the
    toolkit.
    
    <div class="confluence-information-macro confluence-information-macro-note">
    
    <span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>
    
    <div class="confluence-information-macro-body">
    
    **Note:** The toolkit is fully supported and available to all IBM
    z/OS V2 clients at no additional charge.
    
    </div>
    
    </div>

2.  Unzip the file that you downloaded.

3.  Read the Readme file. The Readme file contains information about
    installing and configuring the
    toolkit.
    
    <div class="confluence-information-macro confluence-information-macro-note">
    
    <span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>
    
    <div class="confluence-information-macro-body">
    
    **Note:** We extracted some of the subsequent steps from the Readme
    file and modified the steps as needed.
    
    </div>
    
    </div>

4.  Transfer the pax file in binary format to a USS directory on the
    system on which you want to run `zospt`.

5.  Unpackage the pax file.
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    pax -rf zospt_v#######.pax
    ```
    
    </div>
    
    </div>
    
    The command creates a `zospt` directory.

6.  Ensure that the user ID that is associated with
    the `IZUSVR1` started task has read and execute permissions to all
    directories in the `zospt` path. The z/OSMF setup refers to this
    user ID as `IZUSVR`.

7.  Add `zospt` to
    the `PATH`.
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    export PATH=$PATH:<zospt directory>/bin=
    ```
    
    </div>
    
    </div>
    
    <div class="confluence-information-macro confluence-information-macro-note">
    
    <span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>
    
    <div class="confluence-information-macro-body">
    
    **Note:** The variable that is named `<zospt directory>` is the full
    path to the `zospt` installation directory.
    
    </div>
    
    </div>

8.  Add the toolkit bin to the default profile that resides in
    the `etc` directory. For example:
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    PATH=./:/bin:/usr/sbin:/usr/lpp/NFS:/usr/lpp/Printsrv/bin
    PATH=$PATH:/sys/s390util/bin
    PATH=$PATH:/var/zospt/zospt/bin
    ```
    
    </div>
    
    </div>

9.  Run z/OS Provisioning Toolkit.
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    zospt --help
    ```
    
    </div>
    
    </div>
    
    If the installation was successful, the `zospt --help` output prints
    to the command line.

### Configure the z/OSMF Properties File and Templates

After you install the toolkit, you configure the z/OSMF properties file
and the sample templates. We extracted the following steps from the
Readme file that IBM provides with the installation files and modified
these steps as needed for your z/OSMF
implementation.

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** The toolkit contains a properties file
named `zosmf.properties`. You configure the properties file to let the
toolkit communicate with z/OSMF. The properties file resides in
the `zospt/config` directory.

</div>

</div>

**Follow these steps:**

1.  Test that the properties file is configured properly: 
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    zospt ps
    ```
    
    </div>
    
    </div>

2.  Configure the templates. The sample templates reside in
    the `zospt/templates` directory. To configure templates for your
    environment, copy the sample template directory into a new directory
    within the templates directory. For example, to copy the contents of
    the `..../zospt/templates/cics_53` directory to
    the `.../.zospt/templates/cics_53_copy` directory, issue the
    following
    command:
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    cp -R /var/zospt/zospt/templates/cics_53  /var/zospt/zospt/templates/cics_53_copy
    ```
    
    </div>
    
    </div>

3.  Update (configure) the files and templates that you copied.

4.  Load the copies of the templates into z/OSMF so that you can test
    them.

5.  Edit the associated workflow using the workflow editor. To edit your
    templates, click Edit on the template definition
    page.
    
    <div class="confluence-information-macro confluence-information-macro-warning">
    
    <span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"></span>
    
    <div class="confluence-information-macro-body">
    
    **Important\!** Do not edit the supplied sample workflow. Instead,
    copy the sample workflow directory contents into a new directory and
    update your template definition to refer to the copy.
    
    </div>
    
    </div>

After you complete these steps, you can use the provisioning toolkit to
manage your z/OS development environment. For more information,
see [Getting started with z/OS Provisioning
Toolkit](https://www.ibm.com/support/knowledgecenter/SSXH44E_1.0.0/zospt/zospt-gettingstarted.html).

## Configure z/OSMF Cloud Provisioning

As a systems administrator, you set up the components and plug-ins that
z/OSMF cloud provisioning requires and set up the z/OSMF cloud
provisioning service. <span> </span>

  - [Required z/OS Components and
    Plug-ins](#Configurez/OSManagementFacilityCloudProvisioning-Requiredz/OSComponentsandPlug-ins)
  - [System Requirements for z/OSMF Cloud
    Provisioning](#Configurez/OSManagementFacilityCloudProvisioning-SystemRequirementsforz/OSMFCloudProvisioning)
  - [How z/OSMF Resource Management
    Works](#Configurez/OSManagementFacilityCloudProvisioning-Howz/OSMFResourceManagementWorks)
  - [How z/OSMF Software Services
    Works](#Configurez/OSManagementFacilityCloudProvisioning-Howz/OSMFSoftwareServicesWorks)

### z/OS Requirements and z/OSMF Plug-ins

For information about the components and plug-ins for z/OSMF cloud
provisioning that are required for Brightside CLI, see [Configure z/OS
Management
Facility](433363262.html#Configurez/OSManagementFacility-pre).

### <span>View the z/OSMF Cloud Provisioning Branch</span>

<span><span>The z/OSMF Cloud Provisioning branch in the z/OSMF
navigation tree consists
of </span><span class="confluence-link">Resource
Management</span><span> and </span><span class="confluence-link">Software
Services</span><span>. The information that displays on the navigation
tree in </span>IBM<span> z/OS Management Facility behaves in a manner
that is contingent upon the existence of user IDs in various cloud
provisioning user groups. Consider the following
requirements:</span></span>

  - To view and access Resource Management in the navigation tree, the
    user IDs must be a member of the user group that is designated as
    the Landlord group for the site. Or, the user IDs must be a member
    of a  Domain Administrators group.
  - To view and access Software Services in the navigation tree, the
    user IDs must be a member of the Landlords group, the Domain
    Administrators group, the Approvers group, or a consumer. A consumer
    is a user or a user group that is associated with a tenant.
  - Members of the Resource Pool Administrators group can view and
    access Configuration and Configuration Assistant in the navigation
    tree in the IBM z/OS Management Facility.
  - Members of the WLM Resource Pool Administrators group can view and
    access Performance and Workload Management in the navigation tree in
    IBM z/OS Management Facility.
  - Landlords have access to all domains.
  - Domain Administrators can access only the domains for which they are
    designated as
Administrators.

<div class="confluence-information-macro confluence-information-macro-information">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**More information:**

  - [How z/OSMF Resource Management
    Works](#Configurez/OSManagementFacilityCloudProvisioning-Howz/OSMFResourceManagementWorks)
  - [How z/OSMF Software Services
    Works](#Configurez/OSManagementFacilityCloudProvisioning-Howz/OSMFSoftwareServicesWorks)

</div>

</div>

### How z/OSMF Resource Management Works

As a systems programmer, Resource Management lets you provision domains,
tenants, and resource pools. Resource Management also lets you create
and maintain domains and
tenants.

<div class="confluence-information-macro confluence-information-macro-tip">

<span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Tip:** To learn more about z/OSMF and cloud provisioning, see [What
Cloud Provisioning
is](https://www.ibm.com/support/knowledgecenter/en/SSLTBW_2.2.0/com.ibm.zos.v2r2.izua300/izuconfig_CloudProvSecurityIntro.htm#SummaryCloudProvisioning)
on the IBM Knowledge Center.

</div>

</div>

**Key roles:**

  - **Landlords**  
    Define cloud domains and their associated resources. Designates
    domain administrators.
  - **Domain administrators**  
    Manage domains, define, and manage the relationships for and between
    domain services, tenants, and resource pools.
  - **Resource pool administrators**  
    Manage networking and workload management (WLM) resources in clouds.
  - **Domain Approvers**  
    Approve pending approval records for templates.
  - **Security administrators**  
    Maintain the security management systems for installations. 

With Resource Management, you can perform the following tasks:

  - **Create domains**  
    Users that are designated as Landlords can perform the following
    tasks:
    
      - Specify Resource Pool administrators (Network and WLM)
    
      - Specify Domain Approvers
    
      - Specify the Security Administrator for the Domain
    
      - Specify Domain Administrators

  - **Create tenants**
    
    Users that are designated as Landlords or Domain Administrators can
    perform the following tasks:
    
      - Add Template and Resource Pool
    
      - Add users or user groups for the domain 

### How z/OSMF Software Services Work

As a systems programmer, Software Services lets you create and manage
templates and domains, and create, manage, and provision software
instances.

<div class="confluence-information-macro confluence-information-macro-tip">

<span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Tip:** To learn more about z/OSMF and cloud provisioning, see [What
Cloud Provisioning
is](https://www.ibm.com/support/knowledgecenter/en/SSLTBW_2.2.0/com.ibm.zos.v2r2.izua300/izuconfig_CloudProvSecurityIntro.htm#SummaryCloudProvisioning)
on the IBM Knowledge Center.

</div>

</div>

**Key roles:**

  - **Landlords**  
    Define cloud domains and their associated resources. Designates
    domain administrators.
  - **Domain administrators**  
    Manage domains, define, and manage the relationships for and between
    domain services, tenants, and resource pools.
  - **Domain approvers**  
    Approve pending approval records for templates.

With Software Services, you can perform the following tasks:

  - **Add templates to domains**  
    Users that are designated as Service Providers prepare the
    templates. The user ID for the Service Provider must be identified
    as the Landlord or the Domain Administrator. The user ID for the
    Service Provider must also have read access to the following
    resource profile in the `ZMFAPLA` class:
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    <SAF-prefix>.ZOSMF.PROVISIONING.SOFTWARE_SERVICES
    ```
    
    </div>
    
    </div>

<!-- end list -->

  - **Approve templates**  
    Users that are designated as Approvers for the domain or users that
    can be found in the following properties files for the CICS template
    can approve templates.   
    Changes to the domain, tenant, template, or resource pools can
    change the status of templates, which in turn can cause approval
    records to require re-approval. For example, when z/OSMF recognizes
    changes to the WLM, the template added under the previous version of
    the WLM is invalidated until the WLM under z/OSMF is updated with
    the change.
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    DFH_APPROVER_TSO
    DFH_APPROVER_ZFS
    DFH_APPROVER_CONSOLE
    DFH_APPROVER_SECURITY
    ```
    
    </div>
    
    </div>

<!-- end list -->

  - **Associate templates to tenants**

  - **Provision software from templates**
    
    This task lets you create an instance of the software. To provision
    software from templates, the user ID for the user that is performing
    this task must be defined as a consumer of the template. By default,
    members of the Landlord and the Domain Administrator groups are
    defined as consumers of the templates.

  - **Manage software instances**
    
    To manage software instances, the user ID for the user that is
    performing this task must be defined as a consumer of the
    template. By default, members of the Landlord and the Domain
    Administrator groups are defined as consumers.

## Set Up the z/OSMF Cloud Provisioning Service

As a systems programmer, you set up the cloud provisioning service in
z/OSMF so that users can submit Brightside CLI provisioning commands.

**Follow these steps:**

1.  Open the IBM z/OS Management Facility.

2.  Create your domains. From the z/OSMF navigation tree, expand Cloud
    Provisioning, click Resource Management, click the Actions menu, and
    then click Create Domain. Complete the required fields on the screen
    to create a domain.

3.  Add your templates. From the z/OSMF navigation tree, expand Cloud
    Provisioning, click Software Services, Templates, click the Actions
    menu, and then click Add Template to a Domain. Specify the workflow,
    action, and variable files that the software vendor provided.

4.  (Optional) Add your Network Resource Pools. From the z/OSMF
    navigation tree, expand Configuration, click Configuration
    Assistant, click the Actions menu, and then click Manage z/OS Cloud.
    Complete the required fields to add a Network Resource
    Pool.
    
    <div class="confluence-information-macro confluence-information-macro-note">
    
    <span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>
    
    <div class="confluence-information-macro-body">
    
    **Note:** You perform this step only when the template requires a
    Network Resource Pool.
    
    </div>
    
    </div>

5.  Create your tenants. From the z/OSMF navigation tree, expand Cloud
    Provisioning, click Resource Management, click the Actions menu, and
    then click Create Tenant. Complete the required fields on the screen
    to create a tenant, specify users, the template to use, and the
    information about the Network Resource
    Pool.
    
    <div class="confluence-information-macro confluence-information-macro-note">
    
    <span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>
    
    <div class="confluence-information-macro-body">
    
    **Note:** From Cloud Provisioning, Software Services, there is also
    an action option to associate a tenant.
    
    </div>
    
    </div>

6.  Approve your templates. From the z/OSMF navigation tree, expand
    Cloud Provisioning, click Software Services, click Templates, click
    the Actions menu, and then click Approve Templates. You approve your
    templates under Perform Approvals.

7.  Test your templates. Click the Templates tab and click the check box
    next to the templates that you want to test. Click the Actions menu
    and then click Test. Verify that the templates create your instances
    successfully.

8.  Publish your templates to make them available to users. From the
    Templates tab, click the checkboxes next to the templates that you
    want to publish. Click the Actions menu and then click Publish to
    publish your templates.

9.  Create your software instances. From the navigation tree, click
    Cloud Provisioning, click Software Services, and then click the
    Instances tab. Click the Actions menu and then click Run Templates
    on the menu to create your software instances.

For information about how security administrators configure the security
for z/OSMF cloud provisioning, see [Configure z/OSMF Cloud Provisioning
Security](433363265.html).

## Implement the z/OS Cloud Portal Plug-in

Cloud Provisioning for z/OS includes a sample marketplace and market
administration to make published software services easily available to
consumers. The plug-in lets you make software services available to
marketplace consumers and it adds the Marketplace and Marketplace
Administration tasks to the z/OSMF navigation tree.

Use the z/OSMF Import Manager to implement and remove the
plug-in.

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** The z/OS Cloud Portal Plug-in is an optional component. As a
systems programmer, you can implement the plug-in based on the
requirements of your site. For more information about the plug-in, see
[Updating z/OS for the Cloud Portal
plug-in](https://www.ibm.com/support/knowledgecenter/en/SSLTBW_2.2.0/com.ibm.zos.v2r2.izua300/izuconfig_CloudProvPortalSetup.htm)
on the IBM Knowledge Center.

</div>

</div>

### Implement the Plug-in

To implement the plug-in, specify the following file and click Import:

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
/usr/lpp/zosmf/samples/cloudportal/cloudportal.properties
```

</div>

</div>

### Remove the Plug-in

To remove the plug-in, specify the following file and then click Import:

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
/usr/lpp/zosmf/samples/cloudportal/cloudportaldelete.properties
```

</div>

</div>

### Modify the Plug-in

As a systems programmer, you can modify the plug-in at any time to meet
site requirements. To modify the plug-in, create a copy of your
directory into your directory and then edit and import the copy.

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
