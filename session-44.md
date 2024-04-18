### What we will discuss today ?
    1) Functions 
    2) Dynamic Blocks
    3) Conditions
    4) Networking zero-to-hero

for_each, count (count.index) , if_else

IfElse In Terraform : ( Conditional Expression )
        

    ```
            If condition is true then the result is true_val. If condition is false then the result is false_val.

            condition ? true_val : false_val 
            
    ```

### Use Case : If the BU using this script is saas = t3.medium and any other BU apart from saas should go by t3.micro

Outputs in terraform are not just to display information. 
They play a very important role in sharing the data from one module to other module


What is the purpose of Dynamic Blocks In Terraform ?

When to locals in terraform ?

    When you have a similar pattern and would like to use it or call it on need basis you can use locals.

### Provisioners In Terraform

    Provisioners Help You To Run Actions Or Tasks As apart of the terraform.


    Provisioners marjorly are of 4 types :
        1) Local Provisioner  : This is to run some action on the top of the infra you're running terraform commands
        2) Remote Provisioner   : This is to run some action on the top of the infra you're created by terraform
        3) File Provisioner   : This is used to copy something to the newly creaed infra. ( For this connection provision will also be used )
        4) Connection Provisoner  : To perform something on the top of remote machine : on the created machine, first connection should be enabled and this can be enabled by connection-provisioner.

### Pros and Cons of using List vs Maps ? 

How to use Map of Maps ?


The very first thing that you set you in your company when you decid eto start a project is :
    > Building Network 
    > So, it's quite essential you should know how it works and what to be considered before you start the project.

### Internet vs Intranet 
        Internet : Public Network 
        Intranet : Private Network