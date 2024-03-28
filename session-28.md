
# Today we will speak more on CI , CD , GIT and Branching Strategy

    * GIT 
    * BRANCHING STRATEGY
    * Versioning Strategy


    Windows 7, 8, - , 10, 11

    Versions ? Why we needed ? 
    Each and every version will have some enhancements, bug fixes , additional feature and more support.

    It's always recommended to be on the latest or atleast n-1 version

    Shipping ( Application ) ----> 10 features  -----> Developed by 10 Developers

    Manoj ----> feature-1
    Mike  ----> feature-2
    Mitul ----> feature-3

    How parallel development of an application works ?
    How each and every developer who develops the features know what were the features developed by others ?

    Version Control System & Git Branches 

    What is a branch ? Branch is a copy of code from x-Branch ( main/master )

    What is thin main/master branch ? This is the test copy of the code that's is ready to go to production or code that already went to production.
    This code on main/master branch is the source of truth



# What else on GIT , tomorrow we will see 

        1) git fetch vs git pull    
        2) git rebase
        3) git cherryPick
        4) git log 
        5) git reset vs git checkout commitHast

# How name of the branches should be and what it should represent ? 

    Name of the branch should tell what it is ?

        ----> feature/shipping-dropdown 
        ----> feature/shipping-adding-city 

        ----> bug/city-not-found 
        ----> bug/payment-intermittent-failure 

        ----> hotfix ?

### What is the difference between feature vs bug vs hostfix ?

# Hotfix in Production Deployments

A **hotfix** is a rapid and targeted update applied to a live production system to address critical issues or bugs. It ensures the stability, security, and functionality of the deployed software. Here are the key points:

## Characteristics
- **Urgency**: Hotfixes are urgent and not part of regular release cycles.
- **Minimal Scope**: They focus solely on fixing specific issues.
- **Swift Deployment**: Hotfixes are quickly tested and deployed to production.

## Scenarios for Hotfixes
1. **Critical Bugs**: When severe bugs impact functionality or security.
2. **Security Patches**: To address vulnerabilities promptly.
3. **Data Corruption**: When unexpected data issues occur.
4. **Service Disruptions**: To restore disrupted services.

## Process
1. **Identification**: Identify the critical issue (often through monitoring or user reports).
2. **Development**: Create a fix for the specific problem.
3. **Testing**: Rigorously test the hotfix to prevent unintended side effects.
4. **Deployment**: Apply the hotfix directly to the production environment.
5. **Communication**: Inform stakeholders about the hotfix and its impact.

Remember, hotfixes are essential for maintaining a stable and secure production system. Use them judiciously!


### In software development, each and company has their own BRANCHING STRATEGY ( this is very important know ) 

    There are lot of branching strategies, but anything would fall under these 2 :

            1) Promotion Strategy  ( Famous and highly used )

            2) Release Strategy    ( All the startups and technology agnositic companies uses)