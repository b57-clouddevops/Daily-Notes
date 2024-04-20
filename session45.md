

Point to be notes :
    1) How environments are organized in major projckts  ?
        a) Either all the environments can be on the same AWS Account 
        b) If the infra is quite huge, then we use multiple AWS Accounts for multiple environments. 
        c) Not all the Accounts or the VPC's in the accounts would be having outound access to the internet.
        d) Network Team mains one network account and all the  VPC's in other projects are asked to outbound through that.
        e) All the logs of the all accounts would be coming up to specific account.
        f) In case if you're using more accounts in AWS, to manage easy AWS always recommends to use AWS Landing Zone.


In lab, we are going to build multiple networks based on the environment :
     We have 2 environments :
        1) Prod
        2) Dev
    
    We will provision 2 VPC's : 1) roboshop-dev 2) roboshop-prod

By default, in each adn every regions of AWS Account, AWS Provisions you a default VPC ( network ). Till now we are using it.
It's not recommended to provision infrastructure in default VPC. Because each and every project will have their requests and requirements.

So that's the the first step in any project is Provisioning The Network 

### Points to be provisioned when you want to build a network ?

    1) Understand what's the size of the network that you're interested to build ( for ex: if an office has 10000 exployees : 50000 IP's )
    2) Make sure you subnet the network based on the need ( Breaking the network in to pieces is referred as subneting )
    3) By default one network cannot be communicated by another network ( To enable internal communicaiton : we peering )
        ( Communicaiton between 2 different networks using Privat IP's )
    4) Ensure the selected network range woun't be conflicting with any other network range in the company.

    
### Public vs Private IP 

    Public IP  : This is unique across the world the Internet ( Globally Unique ) : This can be accessed from the internet 
    Private IP : This is unique only with in the netwokr ( that also means you and other company can also use the same IP range )
                 They are only accessible if you're in the same Network.

### Why the concept of private Ip came up



What is DHCP ?
Router vs Switch ?

What are classes in IP Address : 
    

Just by looking at the first octet, we can say which class IP Address it is :

### Classes in private IP Address
    Class A : 10.*.*.*      ( They are used for big networks )
    Class B : 172.*.*.*     ( They are used for big networks )
    Class C : 192.*.*.*     ( They are used for small networks )

### In AWS, what's the biggest network you can created ?
        10.*.*.*/16      ( CIDR )  : This is how you define the size of the network


# Determinte the size of the network ? Ensure the Selected network CIDR should not be overlapped with other cidr
    On Dev : 256    (10.20.0.0/24)
        subnet-1 : 10.20.0.0/25	
        subnet-2 : 10.20.0.128/25

    On prod : 1024  (10.10.0.0/22)


### Public vs Private Subnet     
    Public Subnet  : Machines that are launched in this subnet will have public ip address and may/may not be accessible from the internet.
    Private Subnet : Machines that are launched in this subnet will have only have private ip address and cannot be accessible from the internet.