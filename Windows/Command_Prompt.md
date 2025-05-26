# General Commands
**_cls_** <br>
Clears the terminal screen.

**_dir_** <br>
Lists all the files and folders in the current directory.

**_type <file_name>_** <br>
Displays the contents of a file.

**_tree_** <br>
Displays All the directories and sub-directories in a tree like format.

**_mkdir <dir_name>_** <br>
Creates a new directory.

**_rmdir <dir_name>_** <br>
Removes a directory if empty. 

**_copy <source> <destination>_** <br>
Copies a source file to destination.

**_move <source> <destination>_** <br>
Moves a source file to destination.

**_del <file_name>_** <br>
Deletes file.

**_erase <file_name>_** <br>
Deletes file.

# System Information Commands
**_set_** <br>
Displays environment variables.

**_ver_** <br>
To determine OS version.

**_systeminfo_** <br>
Displays various system information.

**_driverquery_** <br>
Displays all the installed device drivers and their details. (better to pipe it with `more` for pages) <br>
```bash
driverquery | more
```

# Network Commands
**_ipconfig_** <br>
Displays network information.

**_ipconfig /all_** <br>
Displays network information ( Additional details included. )

**_ping <target>_** <br>
Sends ICMP packets to the target server and listens for response. If a response is recieved then the server is UP and RUNNING.

**_tracert <target>_** <br>
Retrieves the route a packet takes to reach the destination.

**_nslookup <target> <name-server [optional]>_** <br>
Retrieves the IP address related to a domain or host.

**_netstat_** <br>
Displays all the established connections. <br>
(Use `-h` for additional arguement details.)

# Process Management Commands
**_tasklist_** <br>
Displays all the running processes.

**_tasklist /?_** <br>
Displays all available filters.

**_tasklist /FI "imagename eq sshd.exe"_** (Sample) <br>
Displays all the process with image name equal to _sshd.exe_.

**_taskkill /PID <process_pid>_** <br>
Kills the process by the process id specified.

# Disk Management Commands
**_chkdsk_** <br>
Checks the file system and disk volumes for errors and bad sectors.

**_sfc /scannow_** <br>
Scans system files for corruption and repairs them if possible.
