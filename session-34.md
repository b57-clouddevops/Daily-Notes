
### What if one of the JOB that you're running on jenkins go crazy and run the the for indefintiely & exhausts the resources ?
    > Jenkins will recounter out of memory or outOfResources error and untimately jenkins will be down which is a potential loss to teams.

### What all could be the reasons on why a machine/server can go down ?

    *   Out Of Memory / CPU / Disk ( resources )
    *   Hardware Failure ( Chip / board / cpu failure / disk failure )
    *   Kernal Panic 

```A kernel panic is a critical system error that halts all operations on a Linux system. It occurs when the Linux kernel, the core of the operating system, encounters an unrecoverable issue and can no longer function safely. Kernel panics can be caused by software bugs or hardware malfunctions.```

#### Common Causes Of Kernal Panic :

```
    Corrupted system files (e.g., initramfs)
    Faulty hardware (e.g., RAM, overheating)
    Incompatible kernel modules
```

### Jenkins-Mastre-Agent Architecture 

    What are the pre-requisties that you need to consider for a node before you add that as a node to as Jenkins Controller ?

        *   Ensure you install JAVA on the top of the NODE ( because Jenkins is a java based product )
        *   Jenkins authenticates using ssh, so make sure you node and jenkins can communicate with each other 
        *   Ensure the security of the NODE Machine has 22 open for the Jenkins Controller ( Jenkins should be able to ssh to the agent machine )

### How can we control the number of jobs that runs on a specfic agent ?
    * We need to define that option while configuring the agent and we refer that as "Number Of Executors"


### If you have 24 nodes that are added to your Jenkins-Controller and you don't have access to them ? How can you see the disk utilization or the space availability on the top of them ?

> You can see that information on the top of Manage Jenkins ---> Nodes ( it shows you the available free space )


### Can we configure warnings in jenkins for the nodes, if any of the nodes of the controller (jenkins) utilize 80% of the disk ?
    *   Yes, that's doable

### If the response time between JENKINS & the agent is not acceptable or if the roundTrip is above the unaccpeted values, can we mark the agent as Offline ? yes
    *   This monitors the round trip network response time from the controller to the agent, and if it goes above a threshold repeatedly, it disconnects the agent.

    *   This is useful for detecting unresponsive agents, or other network problems that clog the communication channel. More specifically, the controller sends a no-op command to the agent, and checks the time it takes to get back the result of this no-op command.

### In how many ways can we add Node to jenkins-controller ?

    *   Adding the node details from the Jenkins-UI 
    *   From the node itself, we can run the JNLP Commands  ( AutoScaling ----> startupScript ( jnlp command) ) 

### How do you backup your Jenkins ?

    * Everyday atleast twict, we will the snapshot of the disk 
    * That will be used when you lost the machine !!!!

### How you upgrade/update your Jenkins ?   

    * Stop the jenkins 
    * Take the back of the workSpace ?  ( Jenkins_Home_Directory : /opt/jenkins/)