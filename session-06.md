1) Recap 
2) Creating server using Launch Template
3) Start with linux basics
4) Create an AMI
5) Create a server from AMI


### How to create a file in linux ?

touch fileName.txt
touch file1.txt  file2.txt  sample.log
touch  .filenames.txt                      ( hidden file )
rm    fileName      to delete a file
# pwd           Displays Present Working Directory



### Every user created on the system will have his own directory in the /home   folder


mike   :   /home/mike/ 
centos :   /home/centos/



cd     :  change directory   :   cd directoryNameToSwitch 

..     : Change / Move 1 directory back






#  cp   : copy and paste
#  mv   : This is used to CUT & Paste a file or rename a file.

$  mv fileNameToBeRenamed   newFileName
$  mv  terraform.txt    b-terraform.txt


$ cp  fileName.txt   fileName.txt.bkp


### Hidden files in linux :

Typically if you wish to save any passwords, tokens or keys, we don't expose them by default.
Instead we create hidden files, which won't be listed with "ls -ltr"

# If you wish to list the hiddle files, you need to use "ls -a"

# To create a hidden file, all you need to do is create a file that starts with "." .password.txt



### Common Storage Asks

1) How to extend the existing disk ?  8 to 15gb ?
2) How to add a new disk to an existing server ?

---------------

1) We take manager approval for additonal storage request 
2) We will raise a request with storage team for storage provisioning 
3) Once they provision, they assign that Storage Unit
4) From the infra team, we have to SCAN for that disk 
5) Once it's recognized, we need to add it.


------------------

1) Now, we go to the terraform and update the value and run the job, it just completes in <15 mins>