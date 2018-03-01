# Using Atlas web Explorers
Atlas provides a sample web client that can be used to view and manipulate JES, data sets, z/OS UNIX System Services (USS), and system logs. The following views are available from the Web UI:
- **JES viewer**

  Use this view to query JES jobs with filters, and view the related steps, files, and status. You can also purge jobs from this view.
- **Syslog**

  Use this view to see the system log by using a web socket. Whenever messages are written, the view is refreshed automatically.

  You can also open a JES spool file for an active job and view its content that is refreshed through a web socket.
- **Dataset Explorer**

  Use this view to browse the MVS™ file system by using a high-level qualifier filter. With Dataset Explorer, you can complete the following tasks:
  - Expand data set members and view the content of data set members.
  - Submit data sets that contain JCL to start a JES job.
  - Open data sets and members in an editor and update the content.
  - Create new data sets by entering attributes or by using the `allocate like` option.
  - Delete data sets and members.
  - Open a data set in a full screen editor, which gives you a fully qualified link to that file. The link can be opened in any browser.
  - Work with an editor that provides basic syntax highlighting and content assist for JCL.
- **UNIX file Explorer**

  Use this view to search and view UNIX files and folders.
