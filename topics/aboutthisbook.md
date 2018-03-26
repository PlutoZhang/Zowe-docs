# About this book
This book describes how to install, configure, and use Giza Closed Beta.  

## Who should read this book
This book is intended for system programmers who are responsible for installing, configuring, developers who want to use Giza to improve z/OS user experience, and anyone who wants to know about Giza.

To use this book, you must be familiar with Mainframe and z/OSMF configuration.

## Terminology used in this book
Before getting started with Giza, please acquaint yourself with the following terms:

|Term|Abbreviation|Definition|
|----|------------|----------|
|Mainframe Virtual Desktop|MVD|Virtual desktop, accessed through a web browser|
|Atlas|N/A|A z/OS RESTful web service and deployment architecture for z/OS microservices|
|Brightside Command Line Interface|||
|z/OS Lightweight User Experience|zLUX|Framework, MVD, plugin applications, TN3270 emulator, and Discovery|
|zLUX Secure Services address space|ZSS|The server that provides secure REST services to support the Giza Node Server|
|Giza Node Server|N/A|Node.js server plus Express.js as webservices framework, and the proxy applications that communicate with the z/OS services and components|
|TN3270|N/A|A limited license Giza plugin that provides a 3270 connection to the mainframe on which the Giza Node Server is running|
|Application|N/A|A plug-in that is an application|
|Discovery|N/A|z/OS subsystems plug-in|


## How to use this book
This book contains an introduction and information for installing, configuring, and using Giza.

[Introducing Giza](introduction.md) explains what is Giza, how it works, and what it can do.

[Installing Giza](installandconfig.md) explains how to install, configure, and maintain Giza so that it can work. It also provides information about troubleshooting installation related problems.

[Using Giza](using.md) explains how to use the features that Giza provides.

## How to send your feedback
Your feedback is important in helping us to provide accurate and high-quality information. If you have comments about this documentation, raise an issue and send us a pull request.

Be sure to include the version of the product, and, if applicable, the specific location (for example, the page number or section heading) of the text that you are commenting on.
