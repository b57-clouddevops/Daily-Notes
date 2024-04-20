### Network Implementation

    1) Provision a vpc
    2) Privision 2 subnets ( one public and one private )
    3) Launch the instance + Create SG ( Scope of the SG is VPC only )
    4) Create an internet-gateway and attach to VPC ( You can have once IGW per VPC.)
        - - - IGW is the entry and exit from the VPC and from the Internet to VPC - - -
    5) Create a Route Table and attach it to the Public Subnet with a route as 0.0.0.0/0 from IGW
    6) Next launch an insance in the private subnet and that won't be having public IP by default due to the subnet property.
    7) Majority of the times, servers in the intranet won't be having public ip address ( 99.9% of the times problems can be avoided if we cut the public ip address ) 
    8) Create a Public NAT GW (  with public ip allocation ) in a subnet ( public-subnet ) that has access to internet.
    9) Create private RT , attach it to the Private Subnet. Now create a route as 0.0.0.0/0 NGW-
    10) Now private machines will get access to the internt.
    11) Still your default network 172.31.*.* network cannot talk to 10 series network and for that we do something called as Network Peering.
    12) If you peer 2 networks, communication between them can be private and 172 and 10 serivces are resolved respectively. 
    13) Create Peering Connection between default and roboshop-dev vpc 
    14) Now update route tables with this peering as route
    15) Post this, default network and roboshop-dev vpc can talk using the private IP Address.

How we would like to implement the public network is :

    1) Public machines should be accessible from the internet and they can talk to the internet 
    2) Private machine should not be accessible from the internet, but if the machines want to talk to the internet, they should be able to  ( that means INSIDE to INTERNET should be enabled )

Assignment for you ? 
    When to use Private NAT. 

Peering between the VPC's : ( Peering only works if source and destination CIDR's won't overlap )
    1) Can be done if both of the are in the same regions or different region
    2) Same account or different account.