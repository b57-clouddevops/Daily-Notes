

Pipeline jobs can allow you to run your job against a designated job.

What if you want to run your job against multiple branches ?
    * Multi Branch Pipeline Job 

        ----> Multi Branch Pipeline and this helps you in allowing the job to run from any branch of your choice without hardcoding 
        ----> You can run the job from a Pull Request ( PR )
        ----> You can also run the job against a TAG
        ----> PR , Git Tag are close to GitHub features, so you need to use the GitHub Plugin 


Tools for lint checks varies for tech to tech :
    if you're using nodejs : jslinst is a famoust lint check tool


It's always recommended to perform password rotation for every 60 days 


Lazy And ( && ) , Lazy Or ( || ) play's a quite important role in making decisions of our choice 

    echo hai && echo ola 

    echo ola || 

As pre your policy, all the PR's can only be approved if the LINT CHECKS and STATIC CODE QUALITY Checks are qualitifed, how can you achieled this ?

```
    Ensure you use the GitHub Plugin and Multi-Branch Pipeline. This gives you the option to run the job against a Pull-Request.

    So, before you approve you can check the job in the jenkins using the PR- Number and based on the job status, you can approve the PR
```

### Jenkins Shared Library

Using this we can place all the common pipeline patterns and can call them on a need basis.



Camel Case:
Words are joined together with the first letter of each subsequent word capitalized (except the first word).
```Example: totalPrice, userName, hasMoreItems.```

Snake_case"
```Example: total_price, user_name, has_more_items.```

We will resume shared-library from tomorrow.