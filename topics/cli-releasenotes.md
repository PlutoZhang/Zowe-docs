
# Zoe Brightside Release Notes </span>
Zoe Brightside is a command-line interface that lets application developers interact with the mainframe in a familiar format. Zoe Brightside helps to increase overall productivity, reduce the learning curve for developing mainframe applications, and exploit the ease-of-use of off-platform tools. Zoe Brightside lets application developers use common tools such as Integrated Development Environments (IDEs), shell commands, bash scripts, and build tools for mainframe development. It provides a set of utilities and services for application developers that want to become efficient in supporting and building z/OS applications quickly.

Zoe Brightside provides the following benefits:

  - Enables and encourages developers with limited z/OS expertise to build, modify, and debug z/OS applications.
  - Fosters the development of new and innovative tools from a PC that can interact with z/OS.
  - Ensure that business critical applications running on z/OS can be maintained and supported by existing and generally available software development resources.
  - Provides a more streamlined way to build software that integrates with z/OS. 

The following sections explain the key features and details for CA
Brightside:

  - [Zoe Brightside Capabilities](#zoe-brightside-capabilities)
  - [Overview Video](#overview-video)
  - [Extend Zoe Brightside](#extend-zoe-brightside)
  - [Participate in the Zoe Brightside Community](#participate-in-the-zoe-brightside-community)
  - [Known Issues](#known-issues)
  - [Report Defects and Issues](#report-defects-and-issues)
  - [Third-Party Software Agreements](#third-party-software-agreements)

**Note:** For information about prerequisites, software requirements, installing and upgrading CA Brightside, see
[Installing Zoe Brightside](cli-installcli.md).

## Zoe Brightside Capabilities

With Zoe Brightside, you can interact with z/OS remotely in the following
ways:

  - **Interact with mainframe files:**   
    Create, edit, download, and
    upload mainframe files (data sets) directly from Zoe Brightside. 
  - **Submit jobs:**    
    Submit JCL from data sets or local storage, monitor the status, and view and download the output automatically.
  - **Issue TSO and z/OS console commands:**    
    Issue TSO and console commands to the mainframe directly from Zoe Brightside.
  - **Integrate z/OS actions into scripts:**    
    Build local scripts that accomplish both mainframe and local tasks. 
  - **Produce responses as JSON documents:**    
    Return data in JSON format on request for consumption in other programming languages.

For more information about the available functionality in Zoe Brightside, see [Zoe Brightside Command Groups](cli-commandgroups.md).

## Overview Video

Click [here](https://www.youtube.com/watch?time_continue=1&v=6WL3p9Or2_4) to watch a brief video and learn more about the product.

## Extend Zoe Brightside

You can install plug-ins to extend the capabilities of Zoe Brightside. Plug-ins add functionality to the product in the form of new command groups, actions, objects, and options.  The following plug-ins are available:

  - CA Endevor® SCM plug-in
  - CA File Master™ Plus plug-in
  - IBM Db2 Database plug-in

For more information, see [Install Plug-ins](cli-installplugins.md).

## Participate in the Zoe Brightside Community
We want to know what you think about CA Brightside. You can participate in the Zoe Brightside community by posting to public forums such as reddit and Slack. With reddit and Slack you can:

  - Tell us what you think about the product. 
  - Ask questions and share your ideas about product enhancements with Zoe Brightside developers and the product management team.

**More Information:**
  - [Additional Resources](cli-additionalresources.md)

## Known Issues 

The following issues are known to exist in this release of CA
Brightside:

  - **Additional syntax required to complete macOS and Linux
    installations.**  
    Depending on how you configured Node.js on Linux or Mac, you might need to add the prefix `sudo `before the `npm install -g` command or the `npm uninstall -g` command. This step gives Node.js write access to the installation directory.

  - **The  `npm install -g` command might fail several times due to an `EPERM` error (Windows).**
    
    This behavior is due to a problem with Node Package Manager (npm) on Windows. There is an open issue on the npm GitHub repository to fix the defect.
    
    If you encounter this problem, some users report that repeatedly attempting to install Zoe Brightside yields success. Some users also report success using the following workarounds:
    
      - Issue the `npm cache clean` command.
      - Uninstall and reinstall CA Brightside. For more information,
        see [Install Zoe Brightside](cli-installcli.md).
      - Issue the `npm install -g brightside --no-optional` command.

  - **The `npm install -g` command might fail due to an `npm ERR! Cannot read property 'pause' of undefined` error.**
    
    This behavior is due to a problem with Node Package Manager (npm). If you encounter this problem, revert to a previous version of npm that does not contain this defect. To revert to a previous version of npm, issue the following command:
    
    `npm install npm@5.3.0 -g`

  - **Node.js commands do not respond as expected.**
    
    When you try to issue node commands and you do not  receive the expected output, there might be a program that is named *node* on your path. The Node.js installer automatically adds a program that is named *node* to your path. When there are pre-existing programs that are  named *node* on your computer, the program that appears
    first in the path is used. To correct this behavior, change the order of the programs in the path so that Node.js appears first.

## Report Defects and Issues
To report problems that you might encounter while using the product, log in to either the Brightside Slack workspace or subreddit. From the forums, you can exchange information with your peers and Brightside developers and subject matter experts. For more information, see [Additional Resources](cli-additionalresources.md).

## Third-Party Software Agreements

Zoe Brightside uses the following third-party
software:

| Third-party Software | Version |
| ----------------- | ------- |
| chalk             | 2.3.0  |
| cli-table2        | 0.2.0  |
| dataobject-parser | 1.2.1  |
| find-up           | 2.1.0  |
| glob              | 7.1.1  |
| js-yaml           | 3.9.0  |
| jsonschema        | 1.1.1  |
| levenshtein       | 1.0.5  |
| log4js            | 2.5.3  |
| merge-objects     | 1.0.5  |
| moment            | 2.20.1 |
| mustache          | 2.3.0  |
| node.js           | 6.11.1 |
| node-ibm\_db      | 2.3.1  |
| node-mkdirp       | 0.5.1  |
| node-progress     | 2.0.0  |
| prettyjson        | 1.2.1  |
| rimraf            | 2.6.1  |
| stack-trace       | 0.0.10 |
| string-width      | 2.1.1  |
| wrap-ansi         | 3.0.1  |
| yamljs            | 0.3.0  |
| yargs             | 8.0.2  |

**Note:** All trademarks, trade names, service marks, and logos referenced herein belong to their respective companies.

To read each complete license, [download the attached zip
file](attachments/473021281/475943312.zip).

**More Information:**

  - [Zoe Brightside Prerequisites](cli-precli.md)
  - [Install Zoe CA Brightside](cli-installcli.md)
  - [Create a Profile](cli-createaprofile.md)
  - [Test Connection to z/OSMF](cli-validateInstallation.md)

