# How to Display Brightside CLI Help
Brightside CLI contains a help system that is embedded directly into the CLI. When you want help with Brightside CLI, you issue various help commands that provide you with information about Brightside CLI, the usage, syntax, actions, and options. You can also display all help, group-level help, and information about the structure of Brightside CLI syntax.

  - [Get Started With Brightside CLI Syntax](#get-started-with-brightside-cli-syntax)
  - [Display All Help](#display-all-help)
  - [Display Group-Level Help](#display-group-level-help)

## Get Started With Brightside CLI Syntax

If you are using Brightside CLI for first time and want to learn more about how to use the syntax (and how Brightside CLI works), open a command line window and issue the following command:

`bright help explain brightside`

To learn how to perform a specific task, or if you want to search for information about a specific command, issue the following command:

`bright help search all <term>`

With this command, Brightside CLI searches and displays help for
information about commands, syntax, descriptions, options, and so on.

**Example:**

`bright help search all dataset`

## Display All Help

To to display all of the Brightside CLI help, open a command line window and issue the following command:

`bright --help`

(Optional) Issue the following command to display all of the Brightside CLI using the alias for the help command:

` bright -h`

## Display Group-Level Help

You can use group-level help to get more information about a specific command group. Use the following syntax to display group-level help and learn more about specific command groups (for example, *cics, projects*, and *zosmf*):

`bright <group name> --help`

**Example:**

` bright compiler --help`

(Optional) Issue the following command to view Brightside CLI group-level help using the alias for the help command:

`bright compiler -h`
