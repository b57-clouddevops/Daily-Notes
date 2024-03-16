# Next Week Starting From Monday/Sunday_Night, we will start with ANSIBLE ----> Jenkins / CICD ----> Terraform ----> Observability


# What's next for today ?
    * I would like to bash to created EC2 Instances & Route53 Records on AWS 


# In how many , can you connect or authenticate to aws ???

    * GUI / Console   ( Username/Userpassowrd)
    * CLI / Commands  ( You would be using tokens for authentication) : But in reality, TOEKN Generation is a pretty bad idea.
            ( Programmatic way )
    Token Generation : Access / Secret Key


# IAM : Identity and access management 
    * We create User Accounts         ( Humans )
    * Group Accounts                  ( Humans )
    * IAM Roles                       ( if one service in AWS wants to talk to other service in AWS, we use IAM Roles )

# IAM helps in achieving Least Privilege Principle ( Zero Trust Principle )

AAA  : Authentication - Authorization - Auditing

In AWS, we have more than 200+ services, but it doesn't mean one service can talk to other service.

EC2 ------->  AWS ( S3 )


IAM Role ----> B57-Admin  -----> Admin Role ----> We will add it to Ec2 
( You can only add one IAM Role Per EC2. But, you can multiple roles to the IAM Role )
( One Ec2 Instance can have n number of security groups )

Vertical Scaling -----> Adding resources to the same machine again and again on the top of it is called as veritcal scaling 
    * Vertical Scaling ( Change of Instance Type from t2.medium to t3.micro : This is always involved downtime ) 
    * how can I scale my Ec2?  Shutdown the ec2 and then change the instance type and then start the server. 
    * We always prefer to go with horizontal scaling.

* Vertical Scaling vs Horizontal Scaling

* Point to be notes : 
    All of your's EC2 Workstation should have an IAM Role with Admin Privileges

# How are we going to create Infra 

    * Using AWS CLI Commands wrappeed in a script!!!!
