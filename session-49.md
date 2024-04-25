
Yesterday we have provisioned the entire network.

Today we are going to start with DB's.

We don't want to maintain DB's ( that are maching critical on the top servers )

In reality, DB's are always preferred ot be on the top of Managed Services ( PaS )

    1) MongoDB      ------->    DocumentDB
    2) Redis        ------->    ElasticCache
    3) MySQL        ------->    RDS ( Postgress, MySQL Aurora , Postgress Aurora , MySQL , SQL Server , Oracle )
    4) RabbitMQ     ------->    AmazonMQ  ( Our application is not compatible with AmazonMQ : So, we stick to RabbitMQ on EC2 only )


Instana supplied code for mongodb is designed to work without userName and password for the database.

But in AWS, DB's won't entertain the authenticaiton without password ( RDS & MYSQL ) :
    To mitigate this, we have taken help from the nodejs developer to make it work from DocumentDB ( a managed service on aws for MongoDB )

Here is the strategy

    root-Module     ------->  terraform-databases 
    backendModules  ------->  tf-module-mysql , tf-module-elasticcache , tf-module-redis , tf-module-rabbitmq

In this session, we will see very nice aspects , challenges and unique use-cases with terraform and we will stick to 100% of the terraform standards.
