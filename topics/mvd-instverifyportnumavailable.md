# Verifying available port numbers

Verify the availability of the ports that are required for zLUX communications.

zLUX requires you to configure the following port numbers in the `zlux-example-server/config/zluxserver.json` configuration file:

-   `zssPort`, which is the port through which the Giza Node Server communicates with the zLUX Secure Services address space. By default, zLUX uses port 8542 for this purpose.
-   An HTTP port for unencrypted access from the browser. By default, zLUX uses port 8543 for this purpose.
-   An HTTPS port for encrypted access from the browser. By default, zLUX uses port 8544 for this purpose.

Complete the following steps:

1.   To determine which ports are not available, follow these steps: 

     - To display a list of ports that are in use, issue the following command:
       ```
       TSO NETSTAT to display
       ``` 
     - To display a list of reserved ports, issue the following command:
       ```
       TSO NETSTAT PORTLIST
       ```  
2.   For the `zssPort`, HTTP and HTTPS ports, select port numbers that are not reserved or already in use. You will need to specify the selected port numbers to complete the procedure in [Setting up the Giza Node server and the zLUX Secure Services address space on z/OS](mvd-instsetupeverythingonzos.md). 
