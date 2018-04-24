# About this book
This book describes how to install, configure, and use Project Giza Closed Beta.  

## Who should read this book
This book is intended for system programmers who are responsible for installing Project Giza, developers who want to use Project Giza to improve z/OS user experience, and anyone who wants to know about Project Giza.

To use this book, you must be familiar with the mainframe and z/OSMF configuration.

## Terminology used in this book
Before getting started with Project Giza, please acquaint yourself with the following terms:

|Term|Abbreviation|Definition|
|--------|-----------|-------------|
|Mainframe Virtual Desktop|MVD|A virtual desktop, accessed through a web browser.|
|Atlas|N/A|A z/OS RESTful web service and deployment architecture for z/OS microservices.|
|Brightside Command Line Interface|Brightside CLI|Lets application developers interact with the mainframe in a format that is natively familiar to them.  It lets application developers use common tools such as Integrated Development Environments (IDEs), shell commands, bash scripts, and build tools for mainframe development.|
|Command Groups|N/A|Command groups focus on specific business processes that application developers and systems programmers perform during their day-to-day activities. |
|Experimental Commands|N/A|Commands that are currently in development and are not ready for general availability. Users can enable or disable these commands. Experimental commands are disabled by default.|
|z/OS Lightweight User Experience|zLUX|zLUX consists of the framework, MVD, plugin applications, TN3270 emulator, and Discovery.|
|zLUX Secure Services address space|ZSS|The server that provides secure REST services to support the Giza Node Server.|
|Giza Node Server|N/A|Node.js server plus Express.js as webservices framework, and the proxy applications that communicate with the z/OS services and components.|
|TN3270|N/A|A limited license Giza plugin that provides a 3270 connection to the mainframe on which the Giza Node Server is running.|
|Application|N/A|A plug-in that is an application.|
|Discovery|N/A|z/OS subsystems plug-in.|

## How to use this book
This book contains an introduction and information for installing and using Project Giza.

- [Project Giza overview](introduction.md) explains what is Project Giza and what it can do.

- [Installing Project Giza](installandconfig.md) explains how to install and maintain Project Giza so that it can work. It also provides information about troubleshooting installation related problems.

- [Using Project Giza](using.md) explains how to use the features that Project Giza provides.

## How to send your feedback
Your feedback is important in helping us to provide accurate and high-quality information. If you have comments about this documentation, you can use the following methods to provide feedback:
- Open an issue in GitHub to request documentation update
- Use the GitHub pull request method

### Opening an issue for the documentation
You can open an issue in Github to request documentation to be updated, improved, or clarified by providing a comment. To do this, complete the following steps.
1. Go to the **Giza-docs** repository in GitHub.
2. Select **Issues**.
3. Click **New issue**.
4. Provide a title and enter your comment on the documenation. Be sure to include the specific location of the text that you are commenting on, for example, the section heading. 
5. Click **Submit new issue**.

### Sending a GitHub pull request
You can provide a suggested edit for the documentation directly in GitHub and send us a pull request. To do this, complete the following steps.
1. Go to the **Giza-docs** repository in GitHub.
2. Locate the specific topic you want to comment on.
3. Make the changes to the file.
4. Scroll to the end of the page and enter a brief description about your change.
5. Optional: Enter an extended description.
6. Select **Create a new branch for this commit and start a pull request**. The documentation team will review and merge your changes.
