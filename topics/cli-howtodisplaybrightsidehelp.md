# Display Zoe Brightside help
Zoe Brightside contains a help system that is embedded directly into the command-line interface. When you want help with Zoe Brightside, you issue help commands that provide you with information about the product, syntax, and usage.

  - [Display top-level help](#display-top-level-help)
  - [Help structure](#help-structure)
  - [Display command group, action, and object help](#display-command-group-action-and-object-help)

## Display top-level help
To begin using the product, open a command line window and issue the following command to view the top-level help descriptions:

```
bright --help
```
**Tip:** The command `bright` initiates the product on a command line. All Zoe Brightside commands begin with `bright.`

## Help structure
The help displays the following types of information:
  - **Description**  
    An explanation of the functionality for the command
    group, action, or option that you specified in a `--help` command.
  - **Usage**  
    The syntax for the command. Refer to usage to determine the expected hierarchical structure of a command.
  - **Options**  
    Flags that you can append to the end of a command to specify particular values or booleans. For example, the volume size
    for a data set that you want to create. 
  - **Global Options**  
    Flags that you can append to any command in Zoe Brightside. For example, the `--help` flag is a global option. 

## Display command group, action, and object help
You can use the `--help` global option get more information about a specific command group, action, or object. Use the following syntax to display group-level help and learn more about specific command groups (for example, *zos-jobs* and *zos-files*):

``` 
bright <group, action, or object name> --help
```
``` 
bright zos-files create --help
```
**More Information:**

  - [Command Groups](cli-commandgroups.md)