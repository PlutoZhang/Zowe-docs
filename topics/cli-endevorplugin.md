# Zoe Brightside Plug-in for  Endevor SCM

As a modern application developer or DevOps Admin, it is helpful to be
able to script DevOps processes using a command-line interface (CLI).

Core CI/CD functions have traditionally been built around lifecycle
capabilities of tools like CA Endevor. Using the CA Endevor plug-in for
Zoe Brightside, developers and DevOps admins can incorporate existing
automation into CI/CD workflows, and leverage it from their laptop or
integrated development environment (IDE). Zoe Brightside brings together
several environments within a single interface, and enables efficient,
streamlined development by removing much of the usual need to switch
between different environments when you create a single code package.

  - [Plug-in
    Overview](#CABrightsidePlug-inforCAEndevorSCM-Plug-inOverview)
  - [Prerequisites](#CABrightsidePlug-inforCAEndevorSCM-Prerequisites)
  - [CA Endevor Plugin for CA
    Brightside](#CABrightsidePlug-inforCAEndevorSCM-CAEndevorPluginforCABrightside)
  - [Use Cases](#CABrightsidePlug-inforCAEndevorSCM-UseCases)
  - [Zoe Brightside
    Commands](#CABrightsidePlug-inforCAEndevorSCM-CABrightsideCommands)

## Plug-in Overview

The CA Endevor plug-in for Zoe Brightside allows you to perform commands
on multiple mainframe applications at once from one terminal window,
without the need to establish several mainframe sessions. This
environment provides you with extensive functionality while saving
technical and time resources.

Zoe Brightside enables you to perform the following actions using the CA
Endevor plug-in without having to step out of the Zoe Brightside
interface:

  - Build code and integrate CA Endevor element code into wider
    packages. 
  - Live interaction between several data sources within a single CLI
    that enables quick comparison and inclusion of data. 
  - Interact with CA Endevor for basic SCM inventory, providing a more
    modern interface experience for end users, which enables easier
    learning and adoption, especially for users previously unfamiliar
    with CA Endevor.

 

## Prerequisites

  - Zoe Brightside installed and configured. For more information,
    see [Install CA Brightside](https://docops.ca.com/display/CMFAAS10/Install+CA+Brightside).
  - CA Endevor instance configured within Endevor web services.
  - Endevor web services installed and running.

## CA Endevor Plugin for Zoe Brightside

To install the Zoe Brightside plug-in, see [Install
Plug-ins](https://docops.ca.com/display/CMFAAS10/Install+Plug-ins).

## Use Cases

  - Brightside commands interact with CA Endevor build actions, enabling more modern interaction
    with CA Endevor.</span><span style="color: rgb(0,0,0);"> </span>
  - Brightside commands interact
    with CA Endevor application lifecycle actions, allowing easy
    scripting from CI/CD
    pipelines.
  - Enables developers to interact
    with CA Endevor for basic SCM inventory actions using the CLI which
    provides an alternate, more UX friendly interface.</span>
  - Enables interaction between CA Endevor including ACL and REST API,
    and CA FileMaster Plus within a single
    CLI<span style="color: rgb(0,0,0);"> </span>
  - Check out/check in of source code assets to a remote location for
    use within a non-mainframe IDE or editor (for example, Sublime,
    Visual Studio Code, IntelliJ IDEA)
  - Build of checked in source for use in unit & functional test
    environments
  - Code packaging and promotion as part of a CI/CD pipeline
  - Approval workflows in response to events in other DevOps tools

## Zoe Brightside Commands

To obtain a current list of the CA Endevor syntax, actions, and options,
open Zoe Brightside and enter the following command:


``` 
bright endevor -h
```
