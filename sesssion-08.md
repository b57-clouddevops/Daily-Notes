# Editors in linux

1) Editors helps us in editiing a file just like how we use a NOTEPAD in windows.

    Ex:  vi ( a default editor , vim ,nano, gedit ) 

2) How to edit a file ?

    ex: vi fileName.txt 

3) vi ( this is case sensitive ) : vi opens the file that you mentioned to edit, if the exists. What if the file you're trying to open doesn't exist ? vi creates the file that you mentioned when you save the content.


4)  vi  works in 3 modes :

        1) ESC Mode 
        2) Colon Mode 
        3) INSERT Mode

5) Search for batch57 and replace that with BATCH57

    ```when doing a search and replace , if you don't use % then it refers only to tha line and if you use % it refers entire file but only the   first occurance in each and everyline and if you want to search and replace all the occurances in the file file then use.

            ex: %s/key/KeyToReplace/g
    ```


6) Common Directories: ( File System in linux )

    /bin/: Contains essential binary executables (commands) used by all users.
    /boot/: Contains boot-related files, including the kernel and bootloader configuration.
    /dev/: Houses device files representing hardware devices (e.g., disks, terminals).
    /etc/: Stores system-wide configuration files.
    /home/: User home directories reside here.
    /lib/: Essential shared libraries.
    /media/: Mount point for removable media (USB drives, CDs).
    /mnt/: Used for temporarily mounting file systems.
    /opt/: Optional software packages.
    /root/: Home directory for the root user.
    /sbin/: System binaries (admin-level commands).
    /srv/: Data for services provided by the system.
    /tmp/: Temporary files (cleared on reboot).
    /usr/: Contains user-related programs, libraries, and documentation.
    /var/: Variable data (logs, caches, spool files).


7) How can I download something from the internet ?  wget  URL 

8) How can I read a file from the internet ? curl urlPath  or curl -O urlPath ( this downloads )

9) How to unzip a file ?  unzip filename.zip 

10) How to create a zip with 3 files ?  zip fileName.zip   file1 file2 file3

11) Linux Run Levels

```
    0 :   Shutdown
    1 :   SINGLE USER MODE  ( During Maintenance )
    2 :   Multi-user Mode without NFS  ( No GUI )
    3 :   Multi User Mode with complete CLI ( Network / NFS wiil available )
    4 :   User-Definable ( Research : Not Commonly Used )
    5 :   Multi user Mode with GUI
    6 :   Restart
```

12) What is sudo and why we need ?
