<div id="page">

<div id="main" class="aui-page-panel">

<div class="aui-page-panel-nav">

<div class="aui-navgroup-inner">

<div id="tabs-nav" class="aui-tabs horizontal-tabs">

  - [**Contents**](#tabs-navigation)
  - [**Search**](#tabs-search)

<div id="tabs-navigation" class="tabs-pane active-pane" data-current-page-id="475943406">

</div>

<div id="tabs-search" class="tabs-pane">

</div>

</div>

</div>

</div>

<div class="section aui-page-panel-content">

<div id="main-header">

<div id="breadcrumb-section">

1.  <span> [CA Brightside Community Edition](index.html) </span>
2.  <span> [Extending](Extending_475935698.html)
</span>

</div>

# <span id="title-text"> CA Brightside Community Edition : CA Brightside Plug-in for IBM Db2 Database </span>

</div>

<div id="content" class="view">

<div class="page-metadata">

</div>

<div id="main-content" class="wiki-content group">

<span class="TextRun SCXW21701336">The CA Brightside plug-in for
IBM </span><span class="TextRun SCXW21701336">Db2 Database lets you
interact with Db2 for z/OS to perform tasks
with </span><span class="TextRun SCXW21701336">modern development tools
to automate typical workloads more efficiently. The plug-in also enables
you to interact with Db2 to advance continuous
integration </span><span class="TextRun SCXW21701336">to</span><span class="TextRun SCXW21701336"> validate
product quality and stability.</span>

<span class="TextRun SCXW21701336"></span>

<div class="toc-macro rbtoc1528725936595">

  - [Plug-in
    Overview](#CABrightsidePlug-inforIBMDb2Database-Plug-inOverview)
  - [Use Cases](#CABrightsidePlug-inforIBMDb2Database-UseCases)
  - [Installation ](#CABrightsidePlug-inforIBMDb2Database-Installation)
  - [Profile Setup](#CABrightsidePlug-inforIBMDb2Database-ProfileSetup)
      - [Create a
        profile](#CABrightsidePlug-inforIBMDb2Database-Createaprofile)
  - [Commands](#CABrightsidePlug-inforIBMDb2Database-Commands)
      - [Call a stored
        procedure ](#CABrightsidePlug-inforIBMDb2Database-Callastoredprocedure)
      - [Execute an SQL
        statement ](#CABrightsidePlug-inforIBMDb2Database-ExecuteanSQLstatement)
      - [Export a table in SQL
        format ](#CABrightsidePlug-inforIBMDb2Database-ExportatableinSQLformat)

</div>

  

<div class="OutlineElement Ltr SCXW21701336">

## <span class="EOP SCXW21701336"><span class="NormalTextRun SCXW4474472">Plug-in Overview</span><span class="EOP SCXW4474472" style="color: rgb(0,0,0);">  
</span></span>

</div>

CA Brightside Plug-in for IBM Db2
Database<span class="TextRun SCXW29463101" style="color: rgb(0,0,0);">
lets you execute SQL statements against a Db2 region, export a Db2
table, and call a stored
procedure. </span><span class="TextRun SCXW29463101" style="color: rgb(0,0,0);">Th</span><span class="TextRun SCXW29463101" style="color: rgb(0,0,0);">e</span><span class="TextRun SCXW29463101" style="color: rgb(0,0,0);"> plug-in
also exposes
its </span><span class="TextRun SCXW29463101" style="color: rgb(0,0,0);">API
so that the plug-in can be used directly in other
products.</span><span class="EOP SCXW29463101" style="color: rgb(0,0,0);"> </span><span style="color: rgb(255,0,0);"> </span>

## <span class="TextRun SCXW4474472" style="color: rgb(0,0,0);">Use Cases</span>

<span class="TextRun SCXW167420990" style="color: rgb(0,0,0);"><span class="NormalTextRun SCXW167420990">Example
use cases for the CA
Brightside</span></span><span class="TextRun SCXW167420990" style="color: rgb(0,0,0);"><span class="NormalTextRun SCXW167420990"> </span></span><span class="TextRun SCXW167420990" style="color: rgb(0,0,0);"><span class="NormalTextRun SCXW167420990">Db2
plug-in</span></span><span class="TextRun SCXW167420990" style="color: rgb(0,0,0);"><span class="NormalTextRun SCXW167420990"> include:</span></span><span class="EOP SCXW167420990" style="color: rgb(0,0,0);"> </span><span style="color: rgb(255,0,0);"> </span>

  - <span class="EOP SCXW29463101"><span class="TextRun SCXW188724242"><span class="NormalTextRun SCXW188724242">E</span></span><span class="TextRun SCXW188724242"><span class="NormalTextRun SCXW188724242">xecute </span></span><span class="TextRun SCXW188724242"><span class="NormalTextRun SCXW188724242">SQL
    and interact with
    databases</span></span><span class="EOP SCXW188724242"> </span></span>
  - <span class="EOP SCXW29463101"><span class="TextRun SCXW46093227"><span class="NormalTextRun SCXW46093227">Execute
    a file with SQL
    statements</span></span><span class="EOP SCXW46093227"> </span></span>
  - <span class="EOP SCXW29463101"><span class="TextRun SCXW117725579"><span class="NormalTextRun SCXW117725579">Export </span></span><span class="TextRun SCXW117725579"><span class="NormalTextRun SCXW117725579">tables </span></span><span class="TextRun SCXW117725579"><span class="NormalTextRun SCXW117725579">to</span></span><span class="TextRun SCXW117725579"><span class="NormalTextRun SCXW117725579"> </span></span><span class="TextRun SCXW117725579"><span class="NormalTextRun SCXW117725579">a
    local file on your
    PC</span></span><span class="TextRun SCXW117725579"><span class="NormalTextRun SCXW117725579"> in
    SQL
    format</span></span><span class="EOP SCXW117725579"> </span></span>
  - <span class="EOP SCXW29463101"><span class="TextRun SCXW89313718"><span class="NormalTextRun SCXW89313718">Call
    a stored procedure and
    pass </span></span><span class="TextRun SCXW89313718"><span class="NormalTextRun SCXW89313718">parameter</span></span><span class="TextRun SCXW89313718"><span class="NormalTextRun SCXW89313718">s</span></span><span class="EOP SCXW89313718"> </span></span>

<span style="color: rgb(255,0,0);"> </span>**<span class="TextRun SCXW4474472" style="color: rgb(0,0,0);">Prerequisite</span><span class="EOP SCXW4474472" style="color: rgb(0,0,0);"> </span>**

<span class="EOP SCXW29463101">Ensure that CA Brightside is
installed.</span>

<div class="confluence-information-macro confluence-information-macro-information">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"></span>

<div class="confluence-information-macro-body">

**More Information:**

  - [Install CA Brightside](Install-CA-Brightside_473021289.html)

</div>

</div>

## <span style="color: rgb(0,0,0);">Installation</span> 

<span class="EOP SCXW29463101">To install the CA Brightside Plug-in for
IBM Db2
Database<span class="TextRun SCXW107684323"><span class="NormalTextRun SCXW107684323">,
issue the following command in the command
shell:</span></span></span><span style="color: rgb(255,0,0);"> </span>

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
$ bright plugins install @brightside/db2 
```

</div>

</div>

To validate the installed plug-in, issue the following
command:<span style="color: rgb(255,0,0);"> </span>

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
$ bright plugins validate db2
```

</div>

</div>

Successful validation of the Db2 plug-in returns the
response: `Successfully
validated`<span style="color: rgb(255,0,0);"> </span>

## <span style="color: rgb(0,0,0);">Profile Setup</span>

<span class="TextRun SCXW90299679" style="color: rgb(36,41,46);"><span class="NormalTextRun SCXW90299679">Before
you start using the Db2 plug-in, create a
profile.</span></span><span class="EOP SCXW90299679" style="color: rgb(0,0,0);">  </span>

### <span style="color: rgb(0,0,0);">Create a profile</span>

<span style="color: rgb(0,0,0);">I<span class="TextRun SCXW217673435" style="color: rgb(36,41,46);"><span class="NormalTextRun SCXW217673435">ssue</span></span><span class="TextRun SCXW217673435" style="color: rgb(36,41,46);"><span class="NormalTextRun SCXW217673435"> the
command </span></span>`-DISPLAY
DDF`<span class="TextRun SCXW217673435" style="color: rgb(36,41,46);"><span class="NormalTextRun SCXW217673435"> in
the SPUFI
or </span></span><span class="TextRun SCXW217673435" style="color: rgb(36,41,46);"><span class="NormalTextRun SCXW217673435">ask
your </span></span><span class="TextRun SCXW217673435" style="color: rgb(36,41,46);"><span class="NormalTextRun SCXW217673435">DBA
for the following
information:</span></span><span class="EOP SCXW217673435"> </span></span>

  - <span style="color: rgb(0,0,0);"><span class="TextRun SCXW107124205" style="color: rgb(36,41,46);">The
    Db2 server host
    name</span></span>
  - <span style="color: rgb(0,0,0);"><span class="TextRun SCXW155438470" style="color: rgb(36,41,46);"><span class="NormalTextRun SCXW155438470">The
    Db2 server port
    number</span></span><span class="EOP SCXW155438470"> </span></span>
  - <span style="color: rgb(0,0,0);"><span class="EOP SCXW155438470"><span class="TextRun SCXW224483324" style="color: rgb(36,41,46);"><span class="NormalTextRun SCXW224483324">The
    database </span></span><span class="TextRun SCXW224483324" style="color: rgb(36,41,46);"><span class="NormalTextRun SCXW224483324">name</span></span><span class="TextRun SCXW224483324" style="color: rgb(36,41,46);"><span class="NormalTextRun SCXW224483324"> (you
    can also use the
    location)</span></span></span></span>
  - <span style="color: rgb(0,0,0);"><span class="EOP SCXW155438470"><span class="EOP SCXW224483324"><span class="TextRun SCXW14593394" style="color: rgb(36,41,46);"><span class="NormalTextRun SCXW14593394">The
    user </span></span><span class="TextRun SCXW14593394" style="color: rgb(36,41,46);"><span class="NormalTextRun SCXW14593394">name</span></span><span class="EOP SCXW14593394"> </span></span></span></span>
  - <span style="color: rgb(0,0,0);"><span class="EOP SCXW155438470"><span class="EOP SCXW224483324"><span class="EOP SCXW14593394"><span class="TextRun SCXW22818517" style="color: rgb(36,41,46);"><span class="NormalTextRun SCXW22818517">The
    password</span></span><span class="EOP SCXW22818517"> </span></span></span></span></span>
  - <span style="color: rgb(0,0,0);"><span class="EOP SCXW155438470"><span class="EOP SCXW224483324"><span class="EOP SCXW14593394"><span class="EOP SCXW22818517"><span class="TextRun SCXW152252826" style="color: rgb(36,41,46);"><span class="NormalTextRun SCXW152252826">If
    your Db2 systems use a secure connection, you can also
    provide </span></span><span class="TextRun SCXW152252826" style="color: rgb(36,41,46);"><span class="NormalTextRun SCXW152252826">a</span></span><span class="TextRun SCXW152252826" style="color: rgb(36,41,46);"><span class="NormalTextRun SCXW152252826">n</span></span><span class="TextRun SCXW152252826" style="color: rgb(36,41,46);"><span class="NormalTextRun SCXW152252826"> SSL/TSL
    certificate
    file.</span></span><span class="EOP SCXW152252826"> </span></span></span></span></span></span>

<span style="color: rgb(0,0,0);"><span class="TextRun SCXW158750049" style="color: rgb(36,41,46);"><span class="NormalTextRun SCXW158750049">To
create a Db2 profile, issue a command in the command shell in the
following
format:</span></span><span class="EOP SCXW158750049"> </span></span><span style="color: rgb(255,0,0);"> </span>

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
$ bright profiles create db2 <profile name> -H <host> -P <port> -d <database> -u <user> -p <password>  
```

</div>

</div>

The profile is created successfully with the following
output:<span style="color: rgb(255,0,0);"> </span>

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
Profile created successfully! Path:
/home/user/.brightside/profiles/db2/<profile name>.yaml
type: db2
name: <profile name>
hostname: <host>
port: <port>
username: securely_stored
password: securely_stored
database: <database>
Review the created profile and edit if necessary using the profile update command.
```

</div>

</div>

## <span style="color: rgb(0,0,0);">Commands  
</span>

<span style="color: rgb(255,0,0);"> </span><span style="color: rgb(0,0,0);">The
following commands can be issued with the CA Brightside Db2
plug-in:</span>

  - [Call a stored
    procedure](#CABrightsidePlug-inforIBMDb2Database-Callastoredprocedure)

  - [Execute an SQL
    statement](#CABrightsidePlug-inforIBMDb2Database-ExecuteanSQLstatement)

  - [Export a table in SQL
    format  
    ](#CABrightsidePlug-inforIBMDb2Database-ExportatableinSQLformat)
    
    <div class="confluence-information-macro confluence-information-macro-tip">
    
    <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"></span>
    
    <div class="confluence-information-macro-body">
    
    **Tip:** At any point, you can issue the help command **`-h`** to
    see a list of available commands.
    
    </div>
    
    </div>

### <span style="color: rgb(0,0,0);">Call a stored procedure</span> 

<span style="color: rgb(0,0,0);">Issue the following command to call a
stored procedure that returns a result set: </span>

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
$ bright db2 call sp "DEMOUSER.EMPBYNO('000120')"
```

</div>

</div>

<span style="color: rgb(0,0,0);">Issue the following command to call a
stored procedure and pass
parameters:</span>

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
$ bright db2 call sp "DEMOUSER.SUM(40, 2, ?)" --parameters 0
```

</div>

</div>

<span style="color: rgb(255,0,0);"> </span><span style="color: rgb(0,0,0);">Issue
the following command to c</span><span style="color: rgb(0,0,0);">all a
stored procedure and pass a placeholder buffer:</span>

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
$ bright db2 call sp "DEMOUSER.TIME1(?)" --parameters "....placeholder..
```

</div>

</div>

### <span style="color: rgb(0,0,0);">Execute an SQL statement</span> 

<span style="color: rgb(0,0,0);">Issue the following command to count
rows in the EMP
table:</span>

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
$ bright db2 execute sql -q "SELECT COUNT(*) AS TOTAL FROM DSN81210.EMP;"
```

</div>

</div>

<span style="color: rgb(0,0,0);">Issue the following command to get a
department name by
ID:</span>

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
$ bright db2 execute sql -q "SELECT DEPTNAME FROM DSN81210.DEPT WHERE DEPTNO='D01'
```

</div>

</div>

### <span style="color: rgb(0,0,0);">Export a table in SQL format </span>

<span style="color: rgb(0,0,0);">Issue the following command to export
the `PROJ` table and save the generated SQL
statements:</span><span style="color: rgb(0,0,0);"> </span>

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
$ bright db2 export table DSN81210.PROJ
```

</div>

</div>

<span style="color: rgb(0,0,0);">Issue the following command to export
the `PROJ`<span> table</span> and save the output to a file:</span>

<div class="code panel caCodePanel">

<div class="codeContent panelContent">

``` ca-code-default
$ bright db2 export table DSN81210.PROJ --outfile projects-backup.sql 
```

</div>

</div>

<span style="color: rgb(0,0,0);">You can also pipe the output to gzip
for on-the-fly compression.</span>

<span style="color: rgb(255,0,0);">  
</span>

</div>

</div>

</div>

</div>

  - <span id="n-473021279">[CA Brightside Community
    Edition](index.html)</span>
      - <span id="n-473021281">[Release
        Notes](Release-Notes_473021281.html)</span>
    <!-- end list -->
      - <span id="n-473021284">[Installing](Installing_473021284.html)</span>
          - <span id="n-473021285">[Prerequisites](Prerequisites_473021285.html)</span>
        <!-- end list -->
          - <span id="n-473021286">[z/OSMF Configuration
            Overview](473021286.html)</span>
              - <span id="n-473021287">[Configure
                z/OSMF](473021287.html)</span>
            <!-- end list -->
              - <span id="n-473021288">[Configure z/OSMF
                Security](473021288.html)</span>
        <!-- end list -->
          - <span id="n-473021289">[Install CA
            Brightside](Install-CA-Brightside_473021289.html)</span>
        <!-- end list -->
          - <span id="n-473021290">[Create a
            Profile](Create-a-Profile_473021290.html)</span>
        <!-- end list -->
          - <span id="n-473021291">[Test Connection to
            z/OSMF](473021291.html)</span>
        <!-- end list -->
          - <span id="n-473021293">[Uninstall CA
            Brightside](Uninstall-CA-Brightside_473021293.html)</span>
    <!-- end list -->
      - <span id="n-475935698">[Extending](Extending_475935698.html)</span>
          - <span id="n-473021292">[Install
            Plug-ins](Install-Plug-ins_473021292.html)</span>
        <!-- end list -->
          - <span id="n-475935700">[CA Brightside Plug-in for CA Endevor
            SCM](CA-Brightside-Plug-in-for-CA-Endevor-SCM_475935700.html)</span>
        <!-- end list -->
          - <span id="n-475935701">[CA Brightside Plug-in for CA File
            Master
            Plus](CA-Brightside-Plug-in-for-CA-File-Master-Plus_475935701.html)</span>
        <!-- end list -->
          - <span id="n-475943406">[CA Brightside Plug-in for IBM Db2
            Database](CA-Brightside-Plug-in-for-IBM-Db2-Database_475943406.html)</span>
    <!-- end list -->
      - <span id="n-473021294">[Using](Using_473021294.html)</span>
          - <span id="n-473021295">[Display
            Help](Display-Help_473021295.html)</span>
        <!-- end list -->
          - <span id="n-473021296">[Command
            Groups](Command-Groups_473021296.html)</span>
    <!-- end list -->
      - <span id="n-473021297">[Additional
        Resources](Additional-Resources_473021297.html)</span>
    <!-- end list -->
      - <span id="n-38207495">[Legal
        Notices](Legal-Notices_38207495.html)</span>

<div id="footer">

<div class="section footer-body">

Copyright © 2018 CA. All rights reserved.

<div class="footer-logo">

</div>

Document generated on Jun 11, 2018 10:05.

</div>

</div>

</div>
