
# Zoe Brightside
Zoe Brightside is a command-line interface that lets application developers interact with the mainframe in a familiar format. Zoe Brightside helps to increase overall productivity, reduce the learning curve for developing mainframe applications, and exploit the ease-of-use of off-platform tools. Zoe Brightside lets application developers use common tools such as Integrated Development Environments (IDEs), shell commands, bash scripts, and build tools for mainframe development. It provides a set of utilities and services for application developers that want to become efficient in supporting and building z/OS applications quickly.

Zoe Brightside provides the following benefits:

  - Enables and encourages developers with limited z/OS expertise to build, modify, and debug z/OS applications.
  - Fosters the development of new and innovative tools from a PC that can interact with z/OS.
  - Ensure that business critical applications running on z/OS can be maintained and supported by existing and generally available software development resources.
  - Provides a more streamlined way to build software that integrates with z/OS. 

The following sections explain the key features and details for Zoe Brightside:

  - [Zoe Brightside capabilities](#zoe-brightside-capabilities)
  - [Extend Zoe Brightside](#extend-zoe-brightside)
  - [Report defects and issues](#report-defects-and-issues)
  - [Third-Party Software Agreements](#third-party-software-agreements)

**Note:** For information about prerequisites, software requirements, installing and upgrading Zoe Brightside, see
[Installing Project Zoe](installandconfig.md).

## Zoe Brightside capabilities

With Zoe Brightside, you can interact with z/OS remotely in the following ways:

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

## Extending Zoe Brightside

You can install plug-ins to extend the capabilities of Zoe Brightside. Plug-ins add functionality to the product in the form of new command groups, actions, objects, and options.  The following plug-ins are available:

  - CA Endevor® SCM plug-in
  - CA File Master™ Plus plug-in
  - IBM Db2 Database plug-in

For more information, see [Installing Plug-ins](cli-installplugins.md).

## Reporting defects and issues
To report problems that you might encounter while using the product, enter issues in the [Brightside GitHub repository](https://github.com/gizafoundation/brightside/issues).

## Third-Party software agreements

Zoe Brightside uses the following third-party software:

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

To read each complete license, navigate to the GitHub repository and download the file named
Zoe_Brightside_TPSRs.zip. The .zip file contains the licenses for all of the third-party components that
Zoe Brightside uses.

**More Information:**

  - [System requirements for Zoe Brightside](cli-precli.md)
  - [Installing Zoe Brightside](cli-installcli.md)
  - [Creating a profile](cli-createaprofile.md)
  - [Testing connection to z/OSMF](cli-validateInstallation.md)
