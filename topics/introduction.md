# Project Zoe overview

Project Zoe offers modern interfaces to interact with z/OS and allows you to work with z/OS in a way that is identical to what you experience on cloud platforms today. You can use these interfaces as delivered or through programmable extensions that are created by clients or third-party vendors.

Project Zoe consists of three main components. Each component provides a different interface.

- zLUX, which contains a browser-based user interface (UI) that provides a full screen interactive experience
- Explorer server, which enables you to access z/OS data, jobs, and subsystems through REST APIs
- Brightside Command Line Interface (Brightside CLI), which provides a command line interface that allows interactive access to those same data, jobs, and subsystem, but extends the capability in additional ways.

For details of each component, see the corresponding section.

## zLUX

zLUX is a product that modernizes and simplifies working on the mainframe. With zLUX, you can create applications to suit your specific needs. zLUX contains a web UI that has the following features:

- The web UI works with the underlying REST APIs for data, jobs, and subsystem, but presents the information in a full screen mode as compared to the command line interface.
- The web UI makes use of the leading-edge web presentation technology and is also extensible through web UI plug-ins to capture and present any variety of information.
- The web UI includes common z/OS developer or system programmer tasks such as an editor for common text-based files like REXX or JCL along with general purpose data set actions for both Unix System Services (USS) and Partitioned Data Sets (PDS) plus Job Entry System (JES) logs.

zLUX consists of the following components:

- **Mainframe Virtual Desktop (MVD)**

    The desktop, accessed through a browser.

- **Zoe Node Server**

    The Node.js server plus the Express.js as a webservices framework, and the proxy applications that communicate with the z/OS services and components.

- **zLUX Secure Services address space**

    A server that provides secure REST services to support the Zoe Node Server.

- **Application plug-ins**

    Several application-type plug-ins are provided. For more information, see [Using zLUX application plug-ins](mvd-appplugins.md).

## Explorer server

The explorer server is a z/OS® RESTful web service and deployment architecture for z/OS microservices. The server is implemented as a Liberty Profile web application that uses z/OSMF services to provide a range of APIs for the management of jobs, data sets, z/OS UNIX™ System Services (USS) files, and persistent data.

These APIs have the following features:

- These APIs are described by the Open API Specification allowing them to be incorporated to any standard-based REST API developer tool or API management process.
- These APIs can be exploited by off-platform applications with proper security controls.

Any client application that calls RESTful APIs directly can use the explorer server.

As a deployment architecture, the explorer server accommodates the installation of other z/Tool microservices into its Liberty instance. These microservices can be used by explorer server APIs and client applications.

## Brightside CLI

Brightside CLI lets application developers interact with the mainframe in a format that is natively familiar to them. Brightside CLI helps to increase overall productivity, reduce the learning curve for developing mainframe applications, and exploit the ease-of-use of off-platform tools.
Brightside CLI lets application developers use common tools such as Integrated Development Environments (IDEs), shell commands, bash scripts, and build tools for mainframe development. It provides a set of utilities and services for application developers who need to quickly become efficient in supporting and building z/OS applications.

With Brightside CLI, you can interact with z/OS remotely in the following ways:

  - **Interact with mainframe files**    

    Create, edit, download, and upload mainframe files (data sets) directly from Brightside CLI. 

  - **Submit jobs**    

    Submit JCL from data sets or local storage, monitor the status, and view and download the output automatically.

  - **Issue TSO and z/OS console commands**    

    Issue TSO and console commands to the mainframe directly    from Brightside CLI.

  - **Provision mainframe environments**    

    Exploit z/OSMF cloud provisioning features to provision environments on-demand.

  - **Integrates z/OS actions**    

    Build local scripts that accomplish both mainframe and local tasks. 

  - **Produce responses as JSON documents**    

    Return data in JSON format on request for consumption in other programming languages.

For more information about the available functionality in Brightside CLI, see [Brightside CLI Command Groups](cli-commandgroups.md).

Brightside CLI provides the following benefits:

  - Enables and encourages developers with limited z/OS expertise to build, modify, and debug z/OS applications.
  - Fosters the development of new and innovative tools from a personal computer that can interact with z/OS operating systems.
  - Ensure that business critical applications running on z/OS can be maintained and supported by existing and generally available software development resources.
  - Provides a more streamlined way to build software that integrates with z/OS platforms.
