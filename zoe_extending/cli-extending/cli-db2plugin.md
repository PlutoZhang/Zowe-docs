# Zoe Brightside plug-in for IBM Db2 Database

The Zoe Brightside plug-in for IBM Db2 Database lets you interact with Db2 for z/OS to perform tasks with modern development tools to automate typical workloads more efficiently. The plug-in also enables you to interact with Db2 to advance continuous integration to validate product quality and stability.

## Plug-in overview

Zoe Brightside Plug-in for IBM Db2 Database lets you execute SQL statements against a Db2 region, export a Db2 table, and call a stored procedure.The plug-in also exposes its API so that the plug-in can be used directly in other products.

## Use cases

Example use cases for Zoe Brightside Db2 plug-in include:

* Execute SQL and interact with databases
* Execute a file with SQL statements
* Export tables to a local file on your PC in SQL format
* Call a stored procedure and pass parameters

## Prerequisites

Ensure that Zoe Brightside is installed.

**More Information:**

* [Installing Zoe Brightside](../../installandconfig/cli-installcli/)

## Installing

There are **two methods** that you can use to install the Zoe Brightside Plug-in for IBM Db2 Database.

**Method 1**

If you installed **Zoe Brightside** from **bintray**, complete the following steps:

1. Open a command line window and issue the following command:

   ```text
    bright plugins install @brightside/db2
   ```

2. After the command execution completes, issue the following command to validate that the installation completed successfully.

   ```text
    bright plugins validate db2
   ```

   Successful validation of the IBM Db2 plug-in returns the response: `Successfully validated`.

**Method 2**

If you downloaded the **Project Zoe** installation package from **Github**, complete the following steps:

1. Open a command line window and change the directory to the location where you extracted the `brightside-bundle.zip` file. If you do not have the `brightside-bundle.zip` file, see the topic **Install Zoe Brightside from local package** in [Installing Zoe Brightside](../../installandconfig/cli-installcli/) for information about how to obtain and extract it.
2. From the command line window, set the `IBM_DB_INSTALLER_URL` environment variable by issuing the following command:
   * Windows operating systems:

     ```text
     set IBM_DB_INSTALLER_URL=%cd%/odbc_cli
     ```

   * Linux and Mac operating systems:

     ```text
     export IBM_DB_INSTALLER_URL=`pwd`/odbc_cli
     ```
3. Issue the following command to install the plug-in:

   ```text
    bright plugins install brightside-db2-1.0.0.tgz
   ```

4. After the command execution completes, issue the following command to validate that the installation completed successfully.

   ```text
    bright plugins validate db2
   ```

   Successful validation of the IBM Db2 plug-in returns the response: `Successfully validated`.

## Profile setup

Before you start using the IBM Db2 plug-in, create a profile.

### Creating a profile

Issue the command `-DISPLAY DDF` in the SPUFI or ask your DBA for the following information:

* The Db2 server host name
* The Db2 server port number
* The database name \(you can also use the location\)
* The user name
* The password
* If your Db2 systems use a secure connection, you can also

  provide an SSL/TSL certificate file.

To create a db2 profile in Zoe Brightside, issue a command in the command shell in the following format:

```text
bright profiles create db2 <profile name> -H <host> -P <port> -d <database> -u <user> -p <password>
```

The profile is created successfully with the following output:

```text
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

## Commands

The following commands can be issued with the Zoe Brightside Db2 plug-in.

**Tip:** At any point, you can issue the help command `-h` to see a list of available commands.

### Calling a stored procedure

Issue the following command to call a stored procedure that returns a result set:

```text
$ bright db2 call sp "DEMOUSER.EMPBYNO('000120')"
```

Issue the following command to call a stored procedure and pass parameters:

```text
$ bright db2 call sp "DEMOUSER.SUM(40, 2, ?)" --parameters 0
```

Issue the following command to call a stored procedure and pass a placeholder buffer:

```text
$ bright db2 call sp "DEMOUSER.TIME1(?)" --parameters "....placeholder..
```

### Executing an SQL statement

Issue the following command to count rows in the EMP table:

```text
$ bright db2 execute sql -q "SELECT COUNT(*) AS TOTAL FROM DSN81210.EMP;"
```

Issue the following command to get a department name by ID:

```text
$ bright db2 execute sql -q "SELECT DEPTNAME FROM DSN81210.DEPT WHERE DEPTNO='D01'
```

### Exporting a table in SQL format

Issue the following command to export the `PROJ` table and save the generated SQL statements:

```text
$ bright db2 export table DSN81210.PROJ
```

Issue the following command to export the `PROJ` table and save the output to a file:

```text
$ bright db2 export table DSN81210.PROJ --outfile projects-backup.sql
```

You can also pipe the output to gzip for on-the-fly compression.

