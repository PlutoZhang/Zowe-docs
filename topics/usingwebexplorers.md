# Using Atlas Web UI
Atlas provides a sample web client that can be used to view and manipulate JES, data sets, z/OS UNIX System Services (USS), and system logs. The following views are available from the Web UI:
- **JES Explorer**

  Use this view to query JES jobs with filters, and view the related steps, files, and status. You can also purge jobs from this view.
- **Syslog**

  Use this view to see the system log by using a web socket. Whenever messages are written, the view is refreshed automatically.

  You can also open a JES spool file for an active job and view its content that is refreshed through a web socket.
- **Dataset Explorer**

  Use this view to browse the MVS™ file system by using a high-level qualifier filter. With the Dataset Explorer, you can complete the following tasks:
  - List the members of partitioned data sets
  - Allocate new datasets and allocate new data sets using the attributes of existing data sets
  - Submit data sets that contain JCL to JES (Job Entry Subsystem).
  - Edit sequential data sets and partitioned dataset members with basic syntax highlighting and content assist for JCL and REXX.
  - Basic validation of record length when editing JCL
  - Delete data sets and members.
  - Open data sets in full screen editor mode, which gives you a fully qualified link to that file. The link is then reusable for example in help tickets
- **UNIX file Explorer**

  Use this view to browse the USS files by using a path. With the UNIX file Explorer, you can complete the following tasks:
  - List files and folders
  - Create new files and folders
  - Edit files with basic syntax highlighting and content assist for JCL and REXX
  - Delete files and folders
