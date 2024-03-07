Domain Name System ( DNS )

    Domain are of 2 types 
        1) Public Domain       ( No Free, you need to buy the domain : This is unique across the internet and DNS is accessible over the internet )
        2) Private Domain      ( It's free in AWS, but not unique across the internet and is accessible only with in the selected network)

Using DNS, we can create DNS Records and DNS Records are of multiple types : 

        1) A Records     : Creating a name to an IP Address
        2) CNAME Record  : Creating a name to an existing


In realiyt in any of the projects, you would'nt be seeing PUBLIC IP Adress to any machine and if that's the case, how can we access the machines from the internet ???

        1) VPN
        2) Jump Host 
        3) Using Sessions Manager

Hosted Zone : 
        1) Public Hosted Zone To Host Public Domains 
        2) Private Hosted To Host Private Domains          :   roboshop.internal

Environments : 
        1) Prod 
        2) Pre-Prod
        3) QA
        4) Dev

Domains based on env's: 
        1) roboshop-dev.internal
        2) roboshop-prod.internal

Or
    roboshop.internal 
        catalogue-dev.roboshop.internal
        catalogue-prod.roboshop.internal

Public Domains are sold by GoDaddy, Hostinger, FreeNom.
    When you buy a domain from one vendor and if you want to move to other vendor with the domain that you bought, they will allow you.


### How are we going to manage and buy a domain ?
    1) Let's assume you already have a domain in your ORG which is maintained on GoDaddy or your internal DNS 
    2) You're planning to move to cloud and would like to Migrate your Domain to Cloud Route 53 due to some advanced features
    3) How are we going to move. 

## Bomain Migration Steps : 
    1) Let's buy a domain  ( AWS or GoDaddy or Hostinger ) and verify it by verifying the email you receive
    2) And then create a Public Hosted Zone On AWS Route53 ( Ensure the name should be the one you bought above )
    3) Copy the NAMESERVERS offered on the Route53 Domain that you've crated
    4) Now open the domain provider where you bought the domain and update the DNS Servers of that domian with the one that are offered in AWS.
    5) Now this is going to take 24 hours for the propagation to complete.
    6) You can validate the domain status on domainchecker.