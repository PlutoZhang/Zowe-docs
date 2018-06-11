#  Zoe Brightside plug-in for CA Endevor SCM

As a modern application developer or DevOps Admin, you need to be able
to script DevOps processes using a command-line interface (CLI).

Core CLI functions have traditionally been built around the lifecycle
capabilities in tools like CA Brightside Community Edition. Using the CA
Brightside Community Edition plugin for CA Brightside, developers and
DevOps admins can incorporate existing automation into CI/CD workflows,
and leverage WHAT from their laptop or integrated development
environment (IDE). CA Brightside brings together several environments
within a single interface, and enables efficient, streamlined
development by removing much of the usual need to switch between
different environments when you create a single code package.

The CA Brightside Community Edition plug-in for CA Endevor
SCM allows you to perform commands on multiple mainframe applications
at once from one terminal window, without the need to establish several
mainframe sessions. This environment provides you with
extensive functionality while saving technical and time resources.

CA Brightside enables you to perform the following actions using the CA
Brightside Community Edition plug-in without having to step out of the
CA Brightside interface:

  - Build code and integrate CA Brightside Community Edition element
    code into wider packages. 
  - Live interaction between several data sources within a single CLI
    that enables quick comparison and inclusion of data. 
  - Interact with CA Brightside Community Edition for basic SCM
    inventory, providing a more modern interface experience for end
    users, which enables easier learning and adoption, especially for
    users previously unfamiliar with CA Brightside Community Edition.


  - [Prerequisites](#CABrightsidePlug-inforCAEndevorSCM-Prerequisites)
  - [CA Endevor Plugin for CA
    Brightside](#CABrightsidePlug-inforCAEndevorSCM-CAEndevorPluginforCABrightside)
  - [Use Cases](#CABrightsidePlug-inforCAEndevorSCM-UseCases)
  - [CA Brightside
    Commands](#CABrightsidePlug-inforCAEndevorSCM-CABrightsideCommands)

## Prerequisites

  - CA Brightside installed and configured. For more information,
    see [Install CA Brightside](Install-CA-Brightside_473021289.html).
  - CA Brightside Community Edition instance configured within Endevor
    web services.
  - Endevor web services installed and running.

## CA Endevor Plugin for CA Brightside

To install the CA Brightside plug-in, see [Install
Plug-ins](Install-Plug-ins_473021292.html).

## Use Cases

  - Brightside commands interacts with CA Brightside Community Edition build actions, enabling more modern interaction with CA Brightside Community Edition. 
  - Brightside commands interact with CA Brightside Community Edition application lifecycle actions, allowing easy scripting from CI/CD pipelines.
  - Enables developers to interact
    with CA Brightside Community Edition for basic SCM inventory
    actions using the CLI which provides an alternate, more UX friendly
    interface.
  - Enables interaction between CA Brightside Community
    Edition including ACL and REST API, and CA FileMaster Plus within a
    single CLI.
  - Check out/check in of source code assets to a remote location for
    use within a non-mainframe IDE or editor (for example, Sublime,
    Visual Studio Code, IntelliJ IDEA)
  - Build of checked in source for use in unit & functional test
    environments
  - Code packaging and promotion as part of a CI/CD pipeline
  - Approval workflows in response to events in other DevOps tools

## CA Brightside Commands

To obtain a current list of the CA Endevor syntax, actions, and options,
open CA Brightside and enter the following command:

``` ca-code-default
bright endevor -h
```

