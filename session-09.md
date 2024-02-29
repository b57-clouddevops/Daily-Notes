 
1) Pipes In Linux ? What is a Pipe in linux ?

 ```    
    PIPE ( | ) this converts the standard output to standard input.
 ```

 standard output 

 standard error 


 [ centos@learn-centos7 ~ ]$ cat /etc/passwd | wc -l
23
[ centos@learn-centos7 ~ ]$ cat /etc/passwd | wc -c
1087

load average: 0.00, 0.01, 0.04 : Load Average gives the Average CPU Utilization of all the allocated CPU's in last 1 5, and 15 Minutes

How to process in the background ?

### User Management  ( creating users, definite passwords, adding users to the group, giving root access using sudo )

what is su ?  switch user : this is used to switch the user account from one user account to other user account ( centos ----> root )
 
what is sudo ? Not everyone in team will have root access, but without root many of the acitvities cannot be done, that why we enroll the needed users to sudo, when you run any command with sudo, that particular command will be executed as a root user and in the system log it says x-user has run the command with sudo.



