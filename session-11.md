### Ownership and Permissions on linux and then Project

By default, each and every file or folder that you create on the server should or will be owned by the person who create it.
That means he is owner of the file & others cannot access this file.

What if others in the system wants to access the file ?

What if I want only Owner should be able Read, Write, Excure the file, but others should just be able to read and should be able to write the file..... ? ownership and permissions.

1) chown is change ownership and helps in giving owner and group related details to the file.

    $ chown owner:groupName nameOfTheFile/Directory
    $ sudo  chown -R centos:devops batch57/

2) What is rwx for any file ???

    $ ls -ltr

    ```
        drwxrwxr-x  2 centos devops   48 Mar  1 00:47 batch57
    
        r - read            = 4
        w - write           = 2
        x - execute         = 1

        rwx   ---> 4+2+1    = 7 
        r-x   ---> 4+0+1    = 5 
        r--   ---> 4+0+0    = 4

    ```

3) How to permissions of a file ? Using chmod

```
    $ chmod  754   fileName 
    $ chmod  -R 754   directoryName/

```

4) What is sticky bit while giving permissions ? Google it!!!!


### What is the best way to implement technology ?

> Always understand what your customer wants or what your business is ? And then based on that thing backwards to pick and apply the technology that fits the use-case.


### Let's Implement a project with the knowledge that we have gained on linux.



5) What is SQL vs No-SQL DB ( Google it : Assignment 




FaceBook Messager -------> Playstore ( apk ) ----> You're running it 
   ( code ) -------> Build Tool ( MAVEN ) ---->  Binary ( .jar / .war /.ear ) (0/1's that only computer can understand)      
                                                ( Artifact : Final Product Of Software Delivery )    


> To run frontend , you need to have a web-server :   apache web-server & nginx 

> To run backend, you need to have app-server :  Apache Tomcat & SprintBoot