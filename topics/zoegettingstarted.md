The Zoe packages are distributed as a pax file that contains the runtimes as well as the scripts to install and launch the z/OS runtime, as well as the runtime for the desktop command line interface.

The zoe-0.8.1 should be transferred to the Unix File System (or USS) of the z/OS system you wish to install and run Zoe from.

1. Transfer the files to z/OS

Navigate your desktop PC or Mac where you have the zoe.pax file in your folder and then connect to z/OS using sftp.
```
sftp userIDorip.of.zos.box
```

If sftp is not available or if you prefer to use ftp you can instead type

```
ftp userID@ip.of.zos.box
```
If you use ftp the file should not be transferred in txt mode as this will corrupt its contents so switch switch to binary file transfer mode by typing
```
bin
```

Once you have connected to z/OS and entered your password you will be entered into the unix file system.  To see what directory you are in type pwd.  Navigate to the directory you wish to transfer the zoe.pax into, using cd to switch directory, ls to list the contents of a directory, and mkdir to create a directory.  

Once you are in the directory you wish to transfer the pax into type put specifying the full file name of the pax file
```
put zoe-0.8.1.pax
```

When the pax file has transferred expand it by typing
```
pax -ppx -rf zoe-0.8.1.pax
```
This will expand to a file structure 

```
  /files
  /install
  /scripts
  ...
```
