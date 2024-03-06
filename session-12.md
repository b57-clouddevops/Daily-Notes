

Each and every user will have a userAccount to signIn . . . and all the objects/files /applications that are configured by the user will be owned by him.

Whenever you leave any project -----> They have to disable & delete your account ----> All the obejcts/files owned by this guy will be gone for-ever.

You should never ever configure the applications with a HUMAN-USER Account.

1) User Account    : This is human users
2) Service Account : This is also a regular user account, created only to configure an application.
3) Group Account   : 

Whenever you want to configure any application, switch to the service-account and you can do the configuration.

Any application server can run n-numbre of applications having said that they should not be having a port conflict.

Always remeber you never ever expose any of the app ip's , ports and that's not at all recommended.


Whenevr you you get in to this, we use redirection using PROXY's!!!!


What is a Proxy vs Reverse Proxy ?


ProxyPass "/student"  "http://172.31.5.248:8080/student/"
ProxyPassReverse "/student"  "http://172.31.5.248:8080/student/"


### What is a Database Schema


<Resource name="jdbc/TestDB" auth="Container" type="javax.sql.DataSource"
               maxTotal="100" maxIdle="30" maxWaitMillis="10000"
               username="student" password="student1" driverClassName="com.mysql.jdbc.Driver"
               url="jdbc:mysql://172.31.13.36:3306/studentapp"/>