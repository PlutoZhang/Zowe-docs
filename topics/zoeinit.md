# Locating system wide environment variables

To prepare the environment, a number of ZFS folders need to be located.  

These are stored in environment variables by adding lines to the user's .profile file.  

Once the environment variables have been set, the `zoe-init.sh` script will not subsequently prompt for them, meaning that multiple installs can be run re-using the same values. To make the environment variables available for different users who may be installing Zoe, the lines setting the environment variables should be set into the /etc/profile file by a user with sufficient privileges.

1. The location where z/OSMF is installed

    The environment variable of $ZOE_ZOSMF_PATH is used. If this is blank, the following default value is tested to see whether this is a valid path to a z/OSMF server.

    ```
    /usr/lpp/zosmf/lib/defaults/servers/zosmfServer
    ```

    If not, a prompt asks where z/OSMF is installed and the environment variable ZOE_ZOSMF_SERVER is set.  

2. The location of a Java 8 64-bit runtime

    The environment variable of $ZOE_JAVA_HIME is used. If the environment variable is blank, a prompt asks for a path to a 64-bit Java 8 directory.  The path must have a child `/bin` folder and the environment variable ZOE_JAVA_HOME is set.

3. The location of an SDSF path

    The environment variable of $ZOE_SDSF_PATH is used. If the environment variable is blank, the following default value is tested to see whether this is a valid path to SDSF.

    ```
    /usr/lpp/sdsf/java
    ```

    If not a prompt asks where SDSF is installed and the environment variable  ZOE_SDSF_PATH is set.

4. The host name of the explorer liberty server

    The environment variable of ZOE_EXPLORER_HOST is used. If the environment variable is not set, then the host name is used to set ZOE_EXPLORER_HOST.
