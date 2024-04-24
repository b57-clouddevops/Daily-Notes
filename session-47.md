Let's implement production grade highly available and fault-tolerant network to host our project.

High Availability : Making sure another set of instances are actively avilable in alteast both the zones. ( Regional vs Zonal High Availability )

Fault-Tolerant : You application should work seem less even in case of any fault in the app

We are building Fault Tolerant Zonal Infrastrcute ( This even accomodates the zonal failure )


Dev VPC  ( 256 )                    :   10.0.0.0/24
    Public-Subnet-1 in us-east-1a   :   10.0.0.0/26
    Public-Subnet-2 in us-east-1b   :   10.0.0.64/26

    Private-Subnet-1 in us-east-1a  :   10.0.0.128/26
    Private-Subnet-2 in us-east-1b  :   10.0.0.192/26	

Prod VPC ( 1024)                    :   10.2.0.0/22
    Public-Subnet-1 in us-east-1a   :   10.2.0.0/24	
    Public-Subnet-2 in us-east-1b   :   10.2.1.0/24

    Private-Subnet-1 in us-east-1a  :   10.2.2.0/24	
    Private-Subnet-2 in us-east-1b  :   10.2.3.0/24	


We are going to use terraform and build the entire network using terraform and it's 100% .
    > The code that you write should work for any network provisioning
    > Just by supplying different values, it should provision a different network.

### How are we going to build the TF Code ?
    1) We go by building our own modules and the user of modules is to keep code dry and re-usable
    2) We will build modules in a separate repo ( refer them as Backend Modules ) and call them from root module


### Terraform Module Sources : 


Terrafile is a GO binary that helps you to download the backend module code from the branch of your choice and keep it locally available to the root module. This way you can source the code form the backend module of your choice

    Steps To Get Terrafile : 
        1) Download Terrafile 
            wget https://github.com/coretech/terrafile/releases/download/v0.7/terrafile_0.7_Linux_i386.tar.gz
        2) Extraxt it , 
            $ tar -xf terrafile
        3) sudo mv terrafile /usr/local/bin/
    
    Terrafile expects the content from where it has to download in a file called as Terrafile ( T in cap' s)

Whenever you're using backend and root modules :
    1) Ensure in the root module, delcare the empty variables of the values that you're supplying in the env.tfvars 
    2) Also declare the empty variables in the backend module 
    3) While calling the module supply them as varName = var.varName.
    