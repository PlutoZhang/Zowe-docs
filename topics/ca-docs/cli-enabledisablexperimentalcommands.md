# Enable and Disable Experimental Commands </span>

Brightside CLI includes experimental commands that are currently in
development and are not ready for general availability. You can enable
or disable these commands. The experimental commands are disabled by
default.

**Important!**  If you use these commands, you might encounter errors,
unexpected behavior, incompatibilities with your system, or incomplete
help text.

## Enable Experimental Commands

To enable the experimental commands, issue the following command:

`bright config set experimental-features enabled `

The experimental commands now appear in your help menu with the prefix
(*experimental)*.To view all available commands, including the
experimental commands, issue the following command: 

`bright -h`

## Disable Experimental Commands

To disable the experimental commands, issue the following command:

`bright config set experimental-features disabled `

## Check Status of Experimental Commands

To determine whether the experimental commands are enabled or disabled,
issue the following command:

`Bright config get
experimental-features`

<div class="confluence-information-macro confluence-information-macro-note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Note:** Experimental commands display the prefix `(experimental)`
in Brightside CLI help when they are enabled. For
example:

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
cics               (experimental) Issue commands to interact with CICS regions 
compiler           (experimental) Compile source code on the mainframe
```

