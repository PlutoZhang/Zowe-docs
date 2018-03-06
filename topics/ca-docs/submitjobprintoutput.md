<div id="page">

<div id="main" class="aui-page-panel">

<div class="aui-page-panel-nav">

<div class="aui-navgroup-inner">

<div id="tabs-nav" class="aui-tabs horizontal-tabs">

  - [**Contents**](#tabs-navigation)
  - [**Search**](#tabs-search)

<div id="tabs-navigation" class="tabs-pane active-pane" data-current-page-id="441193420">

</div>

<div id="tabs-search" class="tabs-pane">

</div>

</div>

</div>

</div>

<div class="section aui-page-panel-content">

<div id="main-header">

<div id="breadcrumb-section">

1.  <span> [Brightside CLI](index.html) </span>
2.  <span> [Using](Using_429365002.html) </span>
3.  <span> [Brightside CLI
    Scenarios](Brightside-CLI-Scenarios_441193419.html)
</span>

</div>

# <span id="title-text"> Brightside CLI : Submit a Job and Print Job Output </span>

</div>

<div id="content" class="view">

<div class="page-metadata">

</div>

<div id="main-content" class="wiki-content group">

As an application developer, you want to change a compile/build job (for
example, change it to compile in 64-bit mode), submit the job to build
your source, and verify that the job output is
correct.<span style="color: rgb(255,0,0);"> </span>

<span style="color: rgb(0,0,0);">In this scenario, you will list your
data sets, specify data set members to edit, make changes using your
preferred editor or integrated development environment (IDE), and submit
the job from the modified mainframe data set. </span>

The following diagram illustrates the tasks to perform in this scenario:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><table>
<caption> </caption>
<tbody>
<tr class="odd">
<td><img src="attachments/441193420/441193422.png" class="gliffy-macro-image" /></td>
</tr>
</tbody>
</table></td>
</tr>
</tbody>
</table>

## **Prerequisites**

To complete this scenario, review the prerequisites that are described
in [Brightside CLI Scenarios](Brightside-CLI-Scenarios_441193419.html).

In addition to the prerequisites listed in [Brightside CLI
Scenarios](Brightside-CLI-Scenarios_441193419.html), this scenario
requires that you have a compile job, compiler options, and source code
that resides in a mainframe data
set.

<div class="confluence-information-macro confluence-information-macro-tip">

<span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**Tip:**  The commands that are used in this scenario target the system
that is specified in your Brightside CLI profile. You can switch
profiles to target different systems.

</div>

</div>

**  
Follow these steps:**

1.  Review the prerequisites.

2.  Open a command line window and issue the following command to list
    all data sets on a
    system:
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    bright zos-files list data-sets "USERID.*"
    ```
    
    </div>
    
    </div>
    
    <div class="confluence-information-macro confluence-information-macro-tip">
    
    <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"></span>
    
    <div class="confluence-information-macro-body">
    
    **Tip:** Use an asterisk \* to view all data sets under the
    specified HLQ (High-Level Qualifier).
    
    </div>
    
    </div>
    
    A list of data sets displays in Brightside CLI.

3.  Issue the following command to list all members in a specified data
    set:
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    bright zos-files list members "USERID.public.compile.jcl"
    ```
    
    </div>
    
    </div>
    
    A list of data set members displays after you issue the command.
    Identify the members that contain JCL and compiler options that you
    want to edit.

4.  Issue the following commands to launch the members that contain the
    JCL and the compiler options in your IDE to edit the code.
    
    1.  Issue the following command to edit the compiler
        options:
        
        <div class="code panel caCodePanel">
        
        <div class="codeContent panelContent">
        
        ``` ca-code-default
        bright zos-files edit data-set "USERID.public.compile.jcl($mtlopt)" --ec code --kw -e jcl
        ```
        
        </div>
        
        </div>
        
        <div class="confluence-information-macro confluence-information-macro-tip">
        
        <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"></span>
        
        <div class="confluence-information-macro-body">
        
        **Tip:** This example shows the command with the following
        command options:
        
          - Use the **--ec** option to launch the code in your IDE. For
            example, **--ec code** launches Visual Studio Code. Refer to
            your IDE documentation to learn the command line syntax to
            launch your IDE.
          - The **--kw** option allows Brightside CLI to watch the local
            files on your personal computer and reflect your changes in
            the mainframe data set.
          - The **-e** option specifies the file extension that you want
            to store the data in locally. For example, `.jcl`.
        
        Issue the `--help `command after any Brightside CLI command to
        see more available options. For more information about getting
        help, see [How to Display Brightside CLI
        Help](How-to-Display-Brightside-CLI-Help_429365003.html).
        
        </div>
        
        </div>
    
    2.  Issue the following command to edit the
        job:
        
        <div class="code panel caCodePanel">
        
        <div class="codeContent panelContent">
        
        ``` ca-code-default
        bright zos-files edit data-set "USERID.public.compile.jcl(enfmtlc)" --ec code --kw -e jcl
        ```
        
        </div>
        
        </div>
        
        The files open in your IDE automatically, as illustrated by the
        following
        screen:
        
        <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size">![Edit
        jcl and compiler options to compile in 64-bit mode in Visual
        Studio Code](attachments/441193420/441193424.png
        "Edit a Job in Visual Studio Code - Before")</span>  

5.  <span style="color: rgb(0,0,0);">In your IDE, edit the compiler
    options file (for example, change to 64-bit) and edit the job file
    (for example, add a comment to say that the job is a 64-bit
    compile). Save your changes in the IDE. Changes are automatically
    reflected in the mainframe data set when you save the files.</span>
    
    <span style="color: rgb(0,0,0);">The following screen illustrates
    changes to the compile options and JCL that enable the job to
    compile source code in 64-bit
    mode:</span>
    
    <span style="color: rgb(0,0,0);"><span class="confluence-embedded-file-wrapper confluence-embedded-manual-size">![Edit
    jcl and compiler options to compile in 64-bit mode in Visual Studio
    Code](attachments/441193420/441193423.png
    "Edit a Job in Visual Studio Code - After")</span>  
    </span>

6.   Issue the following comman<span style="color: rgb(0,0,0);">d to
    s</span>ubmit the job that contains the modified
    JCL:
    
    <div class="code panel caCodePanel">
    
    <div class="codeContent panelContent">
    
    ``` ca-code-default
    bright zos-jobs submit ds "USERID.public.compile.jcl(enfmtlc)" -P
    ```
    
    </div>
    
    </div>
    
    <div class="confluence-information-macro confluence-information-macro-tip">
    
    <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"></span>
    
    <div class="confluence-information-macro-body">
    
    **Tip:** This example shows the **-P** command option, which prints
    all spool output after the job completes.
    
    </div>
    
    </div>
    
    Review the job status and spool output. If the job compiles your
    source code successfully, you completed the scenario\! If the job
    did not complete successfully, repeat Steps 4 through 6 to edit and
    resubmit the job. 
    
      

</div>

</div>

</div>

</div>

  - <span id="n-417294290">[Brightside CLI](index.html)</span>
      - <span id="n-417294291">[Release
        Notes](Release-Notes_417294291.html)</span>
    <!-- end list -->
      - <span id="n-429364995">[Installing](Installing_429364995.html)</span>
          - <span id="n-433363261">[Overview of the z/OS Management
            Facility Configuration Process](433363261.html)</span>
              - <span id="n-433363262">[Configure z/OS Management
                Facility](433363262.html)</span>
            <!-- end list -->
              - <span id="n-433363263">[Configure z/OS Management
                Facility Security](433363263.html)</span>
            <!-- end list -->
              - <span id="n-433363264">[Configure z/OS Management
                Facility Cloud Provisioning](433363264.html)</span>
            <!-- end list -->
              - <span id="n-433363265">[Configure z/OS Management
                Facility Cloud Provisioning
                Security](433363265.html)</span>
        <!-- end list -->
          - <span id="n-429364999">[Install Brightside
            CLI](Install-Brightside-CLI_429364999.html)</span>
        <!-- end list -->
          - <span id="n-430335233">[Validate
            Installation](Validate-Installation_430335233.html)</span>
              - <span id="n-433363269">[Identify and Correct Problems
                Detected by the Validate Profile
                Command](Identify-and-Correct-Problems-Detected-by-the-Validate-Profile-Command_433363269.html)</span>
    <!-- end list -->
      - <span id="n-429365002">[Using](Using_429365002.html)</span>
          - <span id="n-429365003">[How to Display Brightside CLI
            Help](How-to-Display-Brightside-CLI-Help_429365003.html)</span>
        <!-- end list -->
          - <span id="n-447395688">[Brightside CLI Command
            Groups](Brightside-CLI-Command-Groups_447395688.html)</span>
        <!-- end list -->
          - <span id="n-433363274">[Enable and Disable Experimental
            Commands](Enable-and-Disable-Experimental-Commands_433363274.html)</span>
        <!-- end list -->
          - <span id="n-441193419">[Brightside CLI
            Scenarios](Brightside-CLI-Scenarios_441193419.html)</span>
              - <span id="n-441193420">[Submit a Job and Print Job
                Output](Submit-a-Job-and-Print-Job-Output_441193420.html)</span>
    <!-- end list -->
      - <span id="n-38207496">[Legal
        Notices](Legal-Notices_38207496.html)</span>

<div id="footer">

<div class="section footer-body">

Copyright © 2018 CA. All rights reserved.

<div class="footer-logo">

</div>

Document generated on Mar 01, 2018 17:24.

</div>

</div>

</div>
