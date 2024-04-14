

Till now we are good with CI, that means we made Software , tagged it and published it to NEXUS.

Whenever we decide to make Release on any version, using CI/CD we are going to deploy the verison to Infra.

But we don't have infra yet.

How are we managing the infra till now :

    1) First, we created manually.
    2) Next, using AWS CLI Commands wrpped in bash, we are provisioning the infrastructure.

But option 1 and 2 are not even good, because AWS CLI just makes infra provisioning easy, but it's not going to remember the changes made by it, every run provision the infra and which is quite bad.

What's the best way to provision Infrastructure : 

    1) Infrastrcture As Code ( Terraform )

What's the adv with IaC  ?

```
Earlier we used to do less development and more manual work during the RELEASES.

With Terraform, we will put more development effort and during relesae very shorter release and less manual work/operations

That's the whole idea.

```

Terraform is a product from Hashicorp 
> HCL is the language we use to deal terraform ( you can also use python, json , but HCL is preferred. )


What's the alternative's to Terraform ?

    1) Cloud Formation ( But this is IaC only on AWS Cloud )
    2) Pulumi          ( This is still evolving : For dev's, they can create infra by using java, node, go  . . . )

    But with Terraform, it's openSource and cloud agnosistic


Remember, HCL Version & Terraform version are 2 different things.

### How to install terraform ?

```
On your centos8 machine :

    $ sudo yum install -y yum-utils
    $ sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/RHEL/hashicorp.repo
    $ sudo yum -y install terraform
```

### What is the most recent version of terraform ?  1.8.0
### What are the tf versions that you've used in your project ?


### How to check the installed version of terraform ?

```
    $ terraform -v
        Terraform v1.8.0
        on linux_amd64
```

In terraform, everything is a block!!!!

In terraform, all the files should end with .tf / .tfvars / .tfjson . Any other files apart from .tf or .tfvars won't be recognized by terraform.


### Most Commonly Used Terraform Commands :

```
    1) terraform int
    2) terraform plan
    3) terraform apply 
    4) terraform destroy  ( Think 10 times before you run this and this is very unlikey you use. )
```

Basics Of Terraform are enclosed here : https://github.com/b57-clouddevops/terraform-basics.git

Update : 

    1) There are some bugs/some fixes needed for centos-8 & jenkins compatibility.

    2) If you notice slowness on Jenkins when you run it over centos8, don't waste time : Create Jenkins by taking centos-7 [DevOps-LabImage-CentOS7] : Same Credentials and make sure you change the maximum number of jobs as 0 and add your workStation ( centos8 labImage ) as an agent  ( ensure both of them are t3.medium with 20gb disk for better performance )