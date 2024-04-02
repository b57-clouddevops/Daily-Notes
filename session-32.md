# Today we will start with CI/CD using Jenkins

### What is CI ?

Continuous integration is a DevOps software development practice where developers regularly merge their code changes into a central repository, after which automated builds and tests are run. Continuous integration most often refers to the build or integration stage of the software release process and entails both an automation component (e.g. a CI or build service) and a cultural component (e.g. learning to integrate frequently). The key goals of continuous integration are to find and address bugs quicker, improve software quality, and reduce the time it takes to validate and release new software updates.

### Why is Continuous Integration Needed?
In the past, developers on a team might work in isolation for an extended period of time and only merge their changes to the master branch once their work was completed. This made merging code changes difficult and time-consuming, and also resulted in bugs accumulating for a long time without correction. These factors made it harder to deliver updates to customers quickly.


### What is CD ? Continuous Delivery / Continuous Deployment

    * Continuous Delivery: Always ready to deploy, with manual approval.
    * Continuous Deployment: Automatic deployment to production after tests pass.

### Security Scans are of two types :

    1) SAST : Static Application Security Testing ( Checking the overall code quality ) : Static Checks  ( As per OWASP )
                
            i) It verifies the code and identifies if there are any secrets/passwords/tokens are hardcoded in the repo.
            ii) Identifies the duplicate code patterns 
            iii) It also identifies popular vulnerabilties and bad coding standards that are marked in the code as per OWASP 

        Tool : SonarQube , GHAS
    
    2) DAST : Dynamic Application Security Testing ( Once the application deployed, using the known hacking/vulnerability patterns will be executed aganst your application endPoint )

        shipping-v002 ----> shipping-v003

            www.roboshop.com/shipping 
        
        Tool : CheckMarx ( it's a paidTool )


### How can we integrate all the CI/CD Actions that were discussed in today's class ?

In order to achieve this, we need to have a frameWork that's capable of integrating with all the tools.

 ------>   Open Source Framework : Jenkins  ( extensively robust hgh support for integrations )
    
           Java ( Sun Microsystems ) -----> Hubson  ------> Oracle -----> Jenkins ( OpenSource )

-------> What are the alternatives of Jenkins ? ( 95% of the market uses this )

            Azure DevOps, GitHub Actions ( new product ~ 2-3 years ), GitLab CI, Code Fresh ( Not Free )


### Jenkins is all about jobs : 

        1) FreeStyle Jobs    ( v1 )  : GUI 
        2) Pipeline Jobs     ( v2 )  : Everything is a code based approach and we love it

### What is gitops and why gitops approach is preferred in 3 lines ?

```
GitOps manages infrastructure/configuration/process using Git as the source of truth. 

Changes made by committing code to a Git repository, which triggers an automated process to apply those changes in your environment. This approach is preferred because it offers version control, declarative configuration, and easier rollbacks.

```

### Pipeline Jobs are of 3 types :

        1) Scripted Pipelines       ( needs some groovy expertise : very wise way of doing things )
        2) Declarative Pipeline     ( DSL : Jenkins Highly Recommends it)
        3) YAML Approach            ( Future )