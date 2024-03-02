# Patch Management In Linux   ( Updates )

1) Why you need updates/patches of a system or a software/package ?
    a) For additional features
    b) Security fixes 
    c) To fix the performance issues. (1.15.0 ----> 1.15.1)

2) All the systems in corporate has to go through regular patching (udpates) as per the organization policy.

    a) Some organizations has a policy of updating the machines for every 30/45/30/90 days 
    b) Always patching involves restart of system ( we need to stop the stop the applcations that are running ).
    c) This is always supposed to be done during the off-business hours.
    d) In cloud, typically we are going to design the solution even patching should not affect the running applcations.


3) For performing patching on linux, there are lot of ways or Software/ Package/ Patching can be done in 3 ways in any of the linux machines 

    a) Download the needed package from the repository and then ensure all the needed packages for the package you're installing are available and then install the downloaded package ( using rpm )

 ```       Ex: wget https://example.com/file.rpm
               sudo rpm -ivh file.rpm
               sudo rpm -Uvh https://example.com/file.rpm
```
    b) Usage of package manager in linux and this varies based on the flavor and distribution of linux ( recommended option ). When you use yum, all the pre-requisite software for the package-x that you're installing will be handled by the Package manager
```
        ex:  yum       ( fedora / Redhat/ Centos )
             apt-get   ( ubuntu / Debian )
```
    c) Source Code based installation 
     

4) Linux is an OS with thousands of packages and your OS would be needing few of them. By default, any linux comes with default packages installed. 

```
    $ yum list installed    ( shows list of installed packages )
    $ yum list available 
```

5) Google ---> ARM64 vs AMD64 vs RISC vs CISC based CPU Architecture.

6) How to see whether my system needs a restart or nto after updating the patches or packages ?

```
    $ sudo yum install yum-utils
    $ sudo needs-restarting -r
    Core libraries or services have been updated:
    kernel -> 3.10.0-1160.108.1.el7
    systemd -> 219-78.el7_9.9
    linux-firmware -> 20200421-82.git78c0348.el7_9

    Reboot is required to ensure that your system benefits from these updates.

```
sudo yum check-udpate   ( To check whether your systems needs an udpate or not )

7) how to udpate a single package ?

```$ sudo yum udpate curl ```

How to udpate all the packages in a shot ?
```
$ how to downgrade a package
yum downgrade package
```

Create a machine ( from base/community AMI ) -----> Udpate the system, install the needed packages ----> make an ami out of ----> name it as "cento7-payment-29thfeb2023"


# How to run services on linux?
It's based on the os!

```
    centos : systemctl start/stop/restart/status serviceName 

    ubuntu : service service stop
```

### Network Management 

1) In total, 65535 ports are available in any computing based machine that offers networkings.
2) Out of which first 1024 or 0 to 1023 are reserved or the default ports.
3) You built your own service, you configure a port of your choice.

hostname
curl ifconfig.me

sudo netstat -tulpn 

chmod and chown  ( we will see tomorrow )

