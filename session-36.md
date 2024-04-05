
### How can we define the sharedLibrary details in Jenkins ?

Ref : https://www.jenkins.io/doc/book/pipeline/shared-libraries/#using-libraries

You can declared SHARED LIBRARY both at Jenkins Global Level & at job-level as well.

Once you define the sharedLibrary details to the pipeline, any of the functions from this library can be called

```
@Library('shared-library') _

Library declaration should always be in the beginning of the pipeline
```

If you want to pull the functions that are available in a specific branch of the jenkins - shared - library, how can deal that or how can we mention that ?

```
@Library('shared-library@branchName') _
```

### Can we delcared groovy based functions or groovy based syntax in declarative pipelines ?

```
    Yes.
    Enclose your groovy commands in the script { }

    script {

    }
```


If the function ( func ) is delcared in a file names x.groovy and if you're calling fun() from the same file, you can directly call as func()

But if the same fuc() if called from a file called, sample.groovy, then you need to call it using x.func()

### If a Jenkins Job is taking lot of time and when you're trying to terminate using STOP option on ui and if it doesn't work, what would you do.

You can make a POST HTTP Call from UI , using the below options :

```
Pipeline jobs can be stopped by sending an HTTP POST request to URL endpoints of a build.

    BUILD ID URL/stop - aborts a Pipeline.
    BUILD ID URL/term - forcibly terminates a build (should only be used if stop does not work).
    BUILD ID URL/kill - hard kill a pipeline.
```

### Sonarqube :

    1) This is used for codeQuality analysis ( also referred as SAST )
    2) This can be hosted on the top of your own server  
    3) We can also make sure of the SaS Based offering from SonarCloud
    4) SonarQube can be availabled for free with integrated postGress DB, but in org's we go with premium or licences sonarQube, where we will have sonarQube on one server and the backend DB ( portgress ) in a separate server or RDS

### Important Options On SonarQube :

    1) Quality Gate 
    2) Quality Profile 
    3) Code Smell 
    4) Vulnerability
    5) Code Coverage 
    6) Bugs 