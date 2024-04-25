

How to init from a backend file ?
    $ terraform init --backend-config=env-dev/dev-backend.tfvars
    $ terraform plan --var-file=env-dev/dev.tfvars


### We all know that terraform manages the state of the resources created by it!!!

Can terraform manage the properties of any resource that's created manually or which is already there ?
    For some of the resources like routeTable, YES