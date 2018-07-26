# jenkins-master-slave-with-docker
**Resources Created** 
Master Node EC2
Slave Node EC2
EIP's for nodes
ELB and releated AWS resources of EC2 instances

**Working Method**
The cloudformation template will create AN ELB, ec2 instanes (  master and  slave node) EIP to be associated with EC2 instances. The user data will create the necessary environent for ansible playbook. Ansible play book will pull docker images for master and slave on relative node and will bring up the docker container with jenkins running in it. The stack will be based on latest amazon linux ami.  ELB end point can be accessed to check the jenkins. slave node will bear the docker-slave-name in it. 

**Using CF-Template in AWS**
Simply create a cloud formation stack with this template. Any modification required to the ansbile playbooks can be made as per your desire.


**Current Limitations**
###Cloud formation Output will Show case the ELB end point. Wait until the userdata and ansible scripts are completely deployed for the ELB to display the page. 
###No authentication at this moment ( Ananymous login ) 
###3-5 minutes of desployment once the stack creation is completed . ( can be eliminated with minimal changes to ami / by switching code deploy)

**Future improvements**
###use of Autoscaling and code deploy if required
###Porting to terraform 
###ECS usage for infra

**NOTES**
Tested only in Asia Pacific Singapore and EU-Ireland Region 
To work with other regions add Amazonlinux AMI to the template. 
 
Tags
#jenkins #jenkins-master-slave #Master-slave-ci-using-docker #Jenkins-master-slave-with-docker
