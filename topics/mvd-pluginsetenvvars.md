# Setting the environment variables for plug-in development

The UNIX environment variables must be set appropriately before you can use the Project Giza build procedures to develop your own plug-ins.

When you restored the Project Giza archive during the installation and configuration process \([Setting up the Project Giza Node.js server and the ZLUX Secure Services address space on z/OS](mvd-instsetupeverythingonzos.md)\), MVD/build/env.sh was created. You can set the environment variables by editing the env.sh script and then executing it.

1.   Navigate to MVD/build and open env.sh for editing. 
2.   At the top of env.sh, uncomment these lines: 

    ```
    #export NODE_HOME=location-of-node-install-directory
    #export NODE_LIB_HOME=value-of-COMPILER_INSTALL_HLQ-set-when-installing-node-for-z/OS
    #export PATH=location-of-npm-and-other-required-binaries:$PATH:$NODE_HOME/bin
    ```

3.   for the `NODE_HOME`, `NODE_LIB_HOME`, and `PATH` environment variables, replace the text that appears to the right of the equal sign \(`=`\) with the appropriate value for your environment. 
4.   Save env.sh. 
5.   From the MVD/build directory, use the source command in bash to run the modified evn.sh script: source env.sh 

**Parent topic:** [Creating an application plug-in](mvd-plugincreateappplugin.md)

