# Release Notes

Brightside Command Line Interface (Brightside CLI) lets
application developers interact with the mainframe in a format that is
natively familiar to them. Brightside CLI helps to increase overall
productivity, reduce the learning curve for developing mainframe
applications, and exploit the ease-of-use of off-platform tools.
Brightside CLI lets application developers use common tools such
as Integrated Development Environments (IDEs), shell commands, bash
scripts, and build tools for mainframe development. It provides a set of
utilities and services for application developers who need to quickly
become efficient in supporting and building z/OS applications.

Brightside CLI provides the following benefits:

  - Enables and encourages developers with limited z/OS expertise to
    build, modify, and debug z/OS applications.
  - Fosters the development of new and innovative tools from a personal
    computer that can interact with z/OS operating systems.
  - Ensure that business critical applications running on z/OS can be
    maintained and supported by existing and generally available
    software development resources.
  - Provides a more streamlined way to build software that integrates
    with z/OS platforms. 

The following sections explain the key features and details
for Brightside CLI:

  - [Solution Video](#solution-video)
  - [Brightside CLI Capabilities](#brightside-cli-capabilities)
  - [Supported Platforms](#supported-platforms)
  - [Brightside CLI Early Access Preview](#brightside-cli-earley-access-preview)
  - [Participate in the Brightside CLI Community ](#participate-in-the-brightside-cli-community)
  - [Known Issues](#known-issues)
  - [Third-Party Software Agreements](#third-party-software-agreements)

**Note:** For installation, upgrade, and software requirements, see
[Installing.](Installing_429364995.html)

## Solution Video

Watch this short video about how Brightside CLI works. 

## Brightside CLI Capabilities

With Brightside CLI, you can interact with z/OS remotely in the
following ways:

  - **Interact with mainframe files**  
    Create, edit, download, and upload mainframe files (data sets)
    directly from Brightside CLI. 

  - **Submit jobs**  
    Submit JCL from data sets or local storage, monitor the status, and
    view and download the output automatically.

  - **Issue TSO and z/OS console commands**  
    Issue TSO and console commands to the mainframe directly
    from Brightside CLI.

  - **Provision mainframe environments**  
    Exploit z/OSMF cloud provisioning features to provision environments
    on-demand.

  - **Integrates z/OS actions**  
    Build local scripts that accomplish both mainframe and local tasks. 

  - **Produce responses as JSON documents**  
    Return data in JSON format on request for consumption in other
    programming languages.

For more information about the available functionality in Brightside
CLI, see [Brightside CLI Command
Groups](Brightside-CLI-Command-Groups_447395688.html).

## Supported Platforms

**Workstations:** You can install Brightside CLI on any Windows, macOS,
and Linux operating system that supports Node.js version 6 or
later.

**Note:** CA Technologies does not maintain the prerequisite software
that Brightside CLI requires. You are responsible for updating Node.js
and other prerequisites on your personal computer or workstation. We
recommend that you update Node.js regularly to the latest Long Term
Support (LTS) version.

<span class="anchor">**Mainframe systems:** Brightside CLI was designed
and tested to integrate with z/OS Management Facility (z/OSMF) running
on IBM version 2.2 z/OS mainframe systems.</span>

## Brightside CLI Early Access Preview

The Brightside CLI Early Access Preview lets early adopters preview
Brightside CLI. The Release Notes describes new features as they become
available.

Brightside CLI is under continuous development and might have periodic
updates. For information about how to determine your current Brightside
CLI version and apply updates, see [Install Brightside
CLI.](Install-Brightside-CLI_429364999.html)

### Experimental Commands

The Brightside CLI Early Access Preview contains features that are still
under development and have not been tested to GA quality. You can enable
or disable these commands. The experimental commands are disabled by
default.

**Important!** You might encounter problems when using experimental
commands. 

For more information, see [Enable and Disable Experimental
Commands](Enable-and-Disable-Experimental-Commands_433363274.html).

## Participate in the Brightside CLI Community

We want to know what you think about Brightside CLI. You can become a
part of the Brightside CLI community by participating in the [Brightside
CLI project on
validate.ca.com](https://validate.ca.com/project/version/item.html?cap=13283cc32fd9439c85aeb18bba4ac1f6&arttypeid=%7B4109d6e9-6c06-448b-8eb2-6601a5616391%7D&artid=%7B5ACC31C0-2176-437F-B06B-8C572D48C76C%7D).

Visit the Brightside CLI project on Validate.ca.com and navigate to the
relevant section where you can provide the following types of feedback:

  - **Suggestions:** Provide general feedback and make suggestions for
    product enhancements.

  - **Questions:** Ask questions about the product.

  - **Defect Reports:** Report defects that you encounter when using the
    product.

  - **User Forums:** Participate in forums with other Brightside
    CLI early adopters.

Alternatively, you can add comments at the bottom of this DocOps page to
provide feedback on your experience with the product and
documentation.

## Known Issues<span id="ReleaseNotes-knownIssues" class="confluence-anchor-link"></span>

The following issues are known to exist in this release
of Brightside CLI:

  - **Additional syntax required to complete macOS and Linux
    installations.**  
    Depending on how you configured Node.js on Linux or Mac, you might
    need to add the prefix `sudo `before the `npm install -g` command or
    the `npm uninstall -g` command. This step gives Node.js write access
    to the installation directory.

  - **The  `npm install -g` command might fail several times due to
    an `EPERM` error (Windows).**
    
    This behavior is due to a problem with Node Package Manager (npm) on
    Windows. There is an open issue on the npm GitHub repository to fix
    the defect.
    
    If you encounter this problem, some users report that repeatedly
    attempting to install Brightside CLI yields success. Some users also
    report success using the following workarounds:
    
      - Issue the `npm cache clean` command.
      - Uninstall and reinstall Brightside CLI. For more information,
        see [Install BrightSide
        CLI](Install-Brightside-CLI_429364999.html).
      - Issue the `npm install -g brightside --no-optional` command.

  - **The `npm install -g` command might fail due to an `npm ERR! Cannot
    read property 'pause' of undefined` error.**
    
    This behavior is due to a problem with Node Package Manager (npm).
    If you encounter this problem, revert to a previous version of npm
    that does not contain this defect. To revert to a previous version
    of npm, issue the following command:
    
    `npm install npm@5.3.0 -g`

  - **Node.js commands do not respond as expected.**
    
    When you try to issue node commands and you do not receive the
    expected output, there might be a program that is named *node* on
    your path. The Node.js installer automatically adds a program that
    is named *node* to your path. When there are pre-existing programs
    that are named *node* on your computer, the program that appears
    first in the path is used. To correct this behavior, change the
    order of the programs in the path so that Node.js appears first.

To report product defects, visit [Brightside CLI project on
validate.ca.com](https://validate.ca.com/project/version/item.html?cap=13283cc32fd9439c85aeb18bba4ac1f6&arttypeid=%7B4109d6e9-6c06-448b-8eb2-6601a5616391%7D&artid=%7B5ACC31C0-2176-437F-B06B-8C572D48C76C%7D) and
click **Defects** from the **Feedback** menu.

To report documentation issues or make suggestions, place your
comments in the Comments section at the bottom of the applicable
documentation page.

## Third-Party Software Agreements

 Brightside CLI uses the following third-party
software:  

  - ag-grid
  - body-parser
  - chalk
  - cli-table2
  - csv
  - definitelytyped
  - express
  - filewatcher
  - getmdl-select
  - glob
  - i18n
  - jsonschema
  - js-yaml
  - levenshtein
  - lodash
  - log4js
  - material-design-lite
  - mustache
  - Nested-property
  - node.js
  - node-forge
  - node-progress
  - node-tmp
  - opn
  - prettyjson
  - prompt
  - reflect-metadata
  - rimraf
  - simple-ssh
  - stack-trace
  - string-argv
  - wrap-ansi
  - yamljs
  - yargs

**Note:** All trademarks, trade names, service marks, and logos
referenced herein belong to their respective companies.

To read each complete license, <span class="confluence-link">[download
the attached zip
file](attachments/417294291/448246817.zip)</span>[. ](https://docops.ca.com/)

**Note:** For all Early Access Preview releases of Brightside CLI,
download the TPSRs from the [Brightside CLI project on
validate.ca.com](https://validate.ca.com/project/version/item.html?cap=13283cc32fd9439c85aeb18bba4ac1f6&arttypeid=%7B4109d6e9-6c06-448b-8eb2-6601a5616391%7D&artid=%7B5ACC31C0-2176-437F-B06B-8C572D48C76C%7D).

