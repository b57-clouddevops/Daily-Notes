
Starting with variables on Terraform.

# terraform-basics

This repository is to make sure we place and practice all the needed Terraform basics.


terraform init ( This downloads all the needed plugins that are mentioned in the code )

Ensure you run `init` even if you made small changes on that code.

terraform plan  ( This shows plan on what's going to be created / changed / destroyed )

```
    + : Creation 
    - : Destroyed
   -/+: Deleted and created 
    ~ : Some properties will be changed
```

Terraform is not going to create the infra againt and again. It know the created resources and it only deals if there are changes in the code / in the real infrastructure.



### What will happen if you try to use/print a variable where the value of it is not delcared ?
```
    While running the plan / apply, you will be prompted to do that and it's not recommended. Because, we run things through terraform.

```

Under stand this :
```
output "sample_op" {
    value = var.sample
}

Output is reserved key workd to print something and sample_op here is the name of the output

variable "sample" {
    default = "terraform"
}

variable is a reserved key workd to declare/define variable and sample is the name of the variable


```


Note :
    1) You cannot have 2 outputs with the same name
    2) Terraform only support double quotes. Single quotes are not allowed.
    3) Terraform supports Datatypes and by default everything is a string 
        supported data-types :
            1) Strings
            2) Numbers 
            3) Booleans
    4) Strings are always supposed to be enclosed in double-quotes whilst for numbers & booleans, there is no need of it.

    5) terraform supports Dictionary varaible , List Variables , Map Variables 

    6) You can also supply the values of variables in a file called as "terraform.tfvars" and what terraform by default picks this file.
        if you've variables declared in another variables file then "terraform plan --var-file=def.tfvars"


```
output "sample_op" {
    value = var.sample
}

output "sample_op" {
    value = var.ola
}

Invalid

```

### If you've multiples .tf files in a directory and when you run the Terraform init, plan, apply commands how it works ?

    1) terraform first loads all the files in an Alplabetical Order 
    2) It compiles all of them files and then it understands the logic and the order of creation.
    3) Now apply it going to create the infra in an approach that's needed.


It's always recommended to write the infra without hardcoding values that means parameterizing it and supplying the values based on the environment you're provisioning.

### Values of the variables can be sourced from different files and it goes by priority . . . . 


## How to pass a value of a variable from the command line ? By using, -var sample=10

```
    $ terraform init ; terraform plan -var state=Himachal
```

### Variable Precendence : 

Comman line or file.tfvars  >  terraform.auto.tfvars  > terraform.tfvars  > SHELL ENV Variables


#### terraform version vs provider version ?

```
Why do we need to define provider version for terraform

```

### Can we enforce the version of terraform to be used when dealing with provider ?

```
You know aws provider 10.20.40 needs to have a minimum of 1.0.5 terraform version, how can we enforce people to make sure and the terraform commands to fail if they use incorrect terraform version

```


### We would like to create a ec2 instance  by using terraform :

```
    Note :
        1) We are going to run terraform scripts on WORKSTATION
        2) That means workStation has to authenticate with AWS Cloud.
        3) Ensure you've the IAM Role with Admins Permissions attached with WORKSTATION.
```


### What are arguments and attributes in terraform ?

    1) Arguments are the properties that are needed to create infra ( Using these properties we are going to tell the type of infra to be created )

    2) Attributes : These are the properties of the resources that can only the be accessed only once the infrastructure is created.


### What will happen if you run "terraform plan" & "terraform apply" multiples times ?

Is it going to create the resources one more time ? No , because it always refers the state file.


### How terraform works ?

1) All the resources created by terraform will be registered in a file called as STATE FILE in terraform.
2) This statefile contains all the information about the resources created by it.
3) Whenever you do a "TERRAFORM PLAN" , terraform compares your CODE with the STATEFILE and if there are any deviations in relation to the previos infra, terraform marks that as a change and notice that.


### What will happen, I have created the infra using terraform and some changed some properties manually on that console and when you run plan next time, what will happen ? 

    1) If you're terraform, 100% of your actions should only be by terraform.
    2) Manual actions are not entertained.
    3) In this case, if some changes any property manually and if you run the terraform, whatever you've on the code will be the source of truth.
    4) Your manual changes will be erased and the original or the values that are mentioned in the code will only be considered.


### Will "terrafrom apply" only creates the infra ?

    1) No, "terraform apply" can create / destroy / update the resources based on the type of changes that you're making.
    2) So, it's quite important that you need to review the plan 2-3 times along with a peer-review.

Based on the type of changes that you're making 'terraform apply' can create / destroy / update / re-create the infrastructure.


### What is a backend in terraform ?

```
    Backend is nothing but the location where the terraform state file is stored.
    But default, terraform state will be hosted on local machine or on the local-backend.
```

### When you're working in a Team, it's always recommended to keep the STATE centrally, so that everyone in the team can refer and update it.

### Ensure you've a recommended strategy and here are the best practices of placing Terraform remote state :

    1) Ensure your statefile is not a remote-backend 
    2) Make sure that the remote backend is encrypted ( In you're on AWS, use KMS Keys )


    manoj-password   ----- encryptTion ---- xnsheuso ----->  wieovasedrnqvoqijeaasdfqwedfasd

    3) Using Key Management System, generate a key and encrypt the bucket. So that the information is secure and will be security qualified

    4) If you're using S3, ensure versioning is enabled.


#### By the way, what is S3 ?

```
 S3 stands for Simple Secure Storage : This is a object level storage as a solution offered by amazon and which is widely used by companies to store and organize the data and billing is based on the storage utilization
```

### We have placed our state on the top of a remote backend. What will happen if 2 members tries to run the plan or apply at the same time ?

    1) Both of the actions will be executed paralley and it's a quite a back approach.


### How can we place a mechanism, where if some runs the tf and in the meantime if someone in the teams run the TF Apply, the latest apply command should report an ERROR Saying that xyz user is running and you cannot run.

```
We have that feature available if you're using TERRAFORM ENTERPRISE.

But if you're on AWS, you can attach your DYNAMO DB to S3 and can achieve the premium feature for free officially ?

How to do that is something we see in tomorrow's session.
```