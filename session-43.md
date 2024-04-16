
We will cover : Dynamo DB Integration With Remote Backend on AWS with S3 
Terraform basics : functions, conditions and loops


#### Problem Statement :

    1) In Teams, it's not recommended that 2 people running the same infra or terraform job pointing the same infra. 
    2) Recommended approach is, if one person is running the terraform , other person has to wait.
    3) How it's supposed to work is, if one person runs and at the same time if someother person tries to run, he should msg saying that STATEFILE is locked by person - x and you need to wait till the completion of that. 
    4) Point-3 is a default Terraform Enterprise Feature ( TFE : Terraform ) 
    5) Even in openSource you can achieve the same by integrating S3 with DynamoDB ( This is exclusive to AWS )
    6) Typically if you're not on AWS Cloud and if you're using Jenkins to run terraform jobs, you can still handle it :

        a) On the Jenkins job, there is an option called as "disableConcurrentBuilds()" , if a job-x is running and if someone tries to run the same job-x at the same time, till the completion of the previous run, it will be in the queue. 


Advantage of using Terraform Remote backend S3 with dynamodb :

```
    This backend also supports state locking and consistency checking via Dynamo DB, which can be enabled by setting the dynamodb_table field to an existing DynamoDB table name. 

    A single DynamoDB table can be used to lock multiple remote state files. 

    Terraform generates key names that include the values of the bucket and key variables.
```


This is how we can configure our backend on s3 to be managed by DynamodDB :
```
terraform {
  backend "s3" {
    bucket              = "b57-tf-state-bucket"
    key                 = "dev/dynamodb/terraform.tfstate"
    region              = "us-east-1"
    dynamodb_table      = "terraform-locking"
  }
}
```

Ensure DynamodDB is created with partition key as "LockID"


From now if more than one parallel run happens, you'd see the below exception through the state-lock mechanism :

```
    │ Error: Error acquiring the state lock
    │
    │ Error message: operation error DynamoDB: PutItem, https response error StatusCode: 400, RequestID: MBR3VFCDA4QLLGD8ILRNG04RD7VV4KQNSO5AEMVJF66Q9ASUAAJG,
    │ ConditionalCheckFailedException: The conditional request failed
    │ Lock Info:
    │   ID:        aed90da9-cc23-7083-df37-2260f902752e
    │   Path:      b57-tf-state-bucket/dev/dynamodb/terraform.tfstate
    │   Operation: OperationTypeApply
    │   Who:       centos@ip-172-31-35-230.ec2.internal
    │   Version:   1.8.0
    │   Created:   2024-04-16 00:56:44.405457629 +0000 UTC
    │   Info:
    │
    │
    │ Terraform acquires a state lock to protect the state from being written
    │ by multiple users at the same time. Please resolve the issue above and try
    │ again. For most commands, you can disable locking with the "-lock=false"
    │ flag, but this is not recommended.
```


### Ingress vs Egress :

```
    Inboubd Traffic is referred as Ingress 
    Outbound Traffic is referred as Egress
```

### In terraform, how can we fetch the details of the resources that are already available on Cloud ( No need to be created by terraform ) ?

```
    Datasource in terraform can helps in fetching the properties of the available resources.
    Based on the type of resource, terraform provides the datasoures.

    Google ---> AWS AMI Datasource Terraform
```


### What's the challenge with list and count ?

```
 With list and count ( 07-functions example ), you can create multiple instances but with the similar properies, but cannot create multiple instances with different properties of your choice.

 In this case, we can go with something called as MAP based object, a map is nothing but a key with multiple key value pairs along with the usage of Module in terraform
```


### What is a module on terraform ?

```
Modules is nothing but a folder in terraform to organize and keep the terraform code dry.

By default, whatever you write is also in a  root module .

The main advantage of dealing Modules to we can reuse the code and that eventually keeps the code 100% dry.

We can write a module for ec2+sg and this can be used by other teams, just by supplying a different set of values, that's the power of modules

```


### How to create dependency or the order of creation in terraform ?

```
This is not always a safe practice, but when you're dealing with resources that are not know to each other and you want to tell terraform that I need to create this resource-x first and then resource-y. In this case you can use "depends_on"

    in resource-y, mentioned "depends_on= resource-x"

```


### In how many ways, can we use make modules in terraform ?

    1) Hashicorp Supplied Modules   ( Don't use them and it's always better to make your own modules )
    2) Make your own module and keep it locally in the same repo ( Local Modules  : Preferred )
    3) Make your own module and keep it on the top of a remote repository ( Rempte Modules : Remote )


### How to pass/print the outputs from backend module to root module ? How to share the data from one module to another ?



### Steps To Pass The Date Between Modules ?

`Ref : https://github.com/b57-clouddevops/terraform-basics/tree/main/08-localModules`
    1) If you've 2 modules named ec2/ and sg/
    2) And to pass the sdID in form sg module to ec2/, then declare the sdid as output in the sg/ 
    3) Now supply this as abject in the root folder ( sg = module.sg.sdID)
    4) Now on the ec2/ declare an empty variable as variable "sg" {}
    5) Now this can be referrenced 
 