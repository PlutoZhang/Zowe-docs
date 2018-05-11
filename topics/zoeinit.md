To prepare the environment a number of ZFS folders need to be located.  

These are stored in environment variables by adding lines to the user's .profile file.  

Once the environment variables have been set the zoe-init.sh script will not subsequently prompt for them, meaning multiple installs can be run re-using the same values.  To make the environment variables available for different users who may be installing Zoe the lines setting the environment variables should be set into the /etc/profile file by a user with sufficient priveledges.

1. The location of where z/OSMF is installed into

The envrionment variable of $ZOE_ZOSMF_PATH is used
If this is blank the default the value of
 ```
/usr/lpp/zosmf/lib/defaults/servers/zosmfServer
 ```
 is tested to see whether this is a valid path to a z/OSMF server. If not a prompt will ask where z/OSMF is installed and the environment variable ZOE_ZOSMF_SERVER is set.

 2. The location of a Java 8 64 bit runtime

 The environment variable of $ZOE_JAVA_HIME is used.

If the environment variable is blank a prompt will ask for a path to a 64 bit Java 8 directory.  The path  must have a child /bin folder and the environment variable ZOE_JAVA_HOME is set

3. The location of an SDSF path

The environment variable of $ZOE_SDSF_PATH is used

If the envirobnment variable is blank the default value of 
```
/usr/lpp/sdsf/java"
```
is tested to see whether this is a valid path to SDSF.    If not a prompt will ask where SDSF is installed and the environment ZOE_SDSF_PATH variable set.

4. The host name of the explorer-libery-server

The environment variable of ZOE_EXPLORER_HOST is used.  If the environment variable is not set then the hostname is used to set ZOE_EXPLORER_HOST.