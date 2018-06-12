# Zoe Brightside Plug-in for IBM Db2 Database
The CA Brightside plug-in for IBM Db2 Database lets you
interact with Db2 for z/OS to perform tasks with modern development tools to automate typical workloads more efficiently. The plug-in also enables you to interact with Db2 to advance continuous integration to validate product quality and stability.

  - [Plug-in overview](#CABrightsidePlug-inforIBMDb2Database-Plug-inOverview)
  - [Use cases](#CABrightsidePlug-inforIBMDb2Database-UseCases)
  - [Installation ](#CABrightsidePlug-inforIBMDb2Database-Installation)
  - [Profile Setup](#CABrightsidePlug-inforIBMDb2Database-ProfileSetup)
  - [Commands](#Commands)


## Plug-in Overview

CA Brightside Plug-in for IBM Db2
Database lets you execute SQL statements against a Db2 region, export a Db2
table, and call a stored procedure.The plug-in also exposes its API
so that the plug-in can be used directly in other products.

## Use cases

Example use cases for CA Brightside Db2 plug-in include:
  - Execute SQL and interact with databases 
  - Execute a file with SQL statements
  - Export tables to a local file on your PC in SQL format
  - Call a stored procedure and pass parameters

## Prerequisites

Ensure that CA Brightside is installed.

**More Information:**

  - [Install CA Brightside](cli-installcli.md)

## Installation

To install the CA Brightside Plug-in for IBM Db2 Database,
issue the following command in the command shell:

```
$ bright plugins install @brightside/db2 
```

To validate the installed plug-in, issue the following
command:

``` 
$ bright plugins validate db2
```

Successful validation of the Db2 plug-in returns the
response: `Successfully validated`

## Profile setup

Before
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

``` 
$ bright db2 call sp "DEMOUSER.SUM(40, 2, ?)" --parameters 0
```

</div>

</div>

<span style="color: rgb(255,0,0);"> </span><span style="color: rgb(0,0,0);">Issue
the following command to c</span><span style="color: rgb(0,0,0);">all a
stored procedure and pass a placeholder buffer:</span>



```
$ bright db2 call sp "DEMOUSER.TIME1(?)" --parameters "....placeholder..
```

</div>

</div>

### Execute an SQL statement 

Issue the following command to count rows in the EMP table:

``` 
$ bright db2 execute sql -q "SELECT COUNT(*) AS TOTAL FROM DSN81210.EMP;"
```

Issue the following command to get a department name by ID:

``` 
$ bright db2 execute sql -q "SELECT DEPTNAME FROM DSN81210.DEPT WHERE DEPTNO='D01'
```

### Export a table in SQL format

Issue the following command to export the `PROJ` table and save the generated SQL
statements:

``` 
$ bright db2 export table DSN81210.PROJ
```

Issue the following command to export the `PROJ` table and save the output to a file:

``` 
$ bright db2 export table DSN81210.PROJ --outfile projects-backup.sql 
```

You can also pipe the output to gzip for on-the-fly compression.
