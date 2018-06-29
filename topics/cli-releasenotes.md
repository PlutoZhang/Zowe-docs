
# Zoe Brightside
Zoe Brightside is a command-line interface that lets application developers interact with the mainframe in a familiar format. Zoe Brightside helps to increase overall productivity, reduce the learning curve for developing mainframe applications, and exploit the ease-of-use of off-platform tools. Zoe Brightside lets application developers use common tools such as Integrated Development Environments (IDEs), shell commands, bash scripts, and build tools for mainframe development. It provides a set of utilities and services for application developers that want to become efficient in supporting and building z/OS applications quickly.

Zoe Brightside provides the following benefits:

  - Enables and encourages developers with limited z/OS expertise to build, modify, and debug z/OS applications.
  - Fosters the development of new and innovative tools from a PC that can interact with z/OS.
  - Ensure that business critical applications running on z/OS can be maintained and supported by existing and generally available software development resources.
  - Provides a more streamlined way to build software that integrates with z/OS. 

The following sections explain the key features and details for Zoe Brightside:

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

  - IBM Db2 Database plug-in

For more information, see [Installing Plug-ins](cli-installplugins.md).

## Reporting defects and issues
To report problems that you might encounter while using the product, enter issues in the [Brightside GitHub repository](https://github.com/gizafoundation/brightside/issues).

## Third-Party software agreements

Zoe Brightside uses the following third-party software:

| Third-party Software | Version | File name             |
| ----------------- | -------| ------------------------- |
| chalk             | 2.3.0  | Legal_Doc_00002285_56.pdf |
| cli-table2        | 0.2.0  | Legal_Doc_00002310_5.pdf  |
| dataobject-parser | 1.2.1  | Legal_Doc_00002310_36.pdf |
| find-up           | 2.1.0  | Legal_Doc_00002310_33.pdf |
| glob              | 7.1.1  | Legal_Doc_00001713_45.pdf |
| js-yaml           | 3.9.0  | Legal_Doc_00002310_16.pdf |
| jsonfile          | 4.0.0  | Legal_Doc_00002310_40.pdf |
| jsonschema        | 1.1.1  | Legal_Doc_00002310_17.pdf
| levenshtein       | 1.0.5  | See [UNLICENSE](https://github.com/gf3/Levenshtein/blob/master/UNLICENSE) |
| log4js            | 2.5.3  | Legal_Doc_00002310_37.pdf |
| merge-objects     | 1.0.5  | Legal_Doc_00002310_34.pdf |
| moment            | 2.20.1 | Legal_Doc_00002285_25.pdf |
| mustache          | 2.3.0  | Legal_Doc_mustache.pdf    |
| node.js           | 6.11.1 | Legal_Doc_nodejs.pdf      |
| node-ibm\_db      | 2.3.1  | Legal_Doc_00002310_38.pdf |
| node-mkdirp       | 0.5.1  | Legal_Doc_00002310_35.pdf |
| node-progress     | 2.0.0  | Legal_Doc_00002310_7.pdf  |
| prettyjson        | 1.2.1  | Legal_Doc_00002310_22.pdf |
| rimraf            | 2.6.1  | Legal_Doc_00002310_8.pdf  |
| stack-trace       | 0.0.10 | Legal_Doc_00002310_10.pdf |
| string-width      | 2.1.1  | Legal_Doc_00002310_39.pdf |
| wrap-ansi         | 3.0.1  | Legal_Doc_00002310_12.pdf |
| yamljs            | 0.3.0  | Legal_Doc_00002310_13.pdf |
| yargs             | 8.0.2  | Legal_Doc_00002310_1.pdf  |

**Note:** All trademarks, trade names, service marks, and logos referenced herein belong to their respective companies.

To read each complete license, navigate to the GitHub repository and download the file named
Zoe_Brightside_TPSRs.zip. The .zip file contains the licenses for all of the third-party components that
Zoe Brightside uses.

**More Information:**

  - [System requirements for Zoe Brightside](cli-precli.md)
  - [Installing Zoe Brightside](cli-installcli.md)
  - [Creating a profile](cli-createaprofile.md)
  - [Testing connection to z/OSMF](cli-validateInstallation.md)
