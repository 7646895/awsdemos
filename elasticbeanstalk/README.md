# AWS Elastic Bean Stalk Lab #1

#### Whats covered in this demo?
1. Basic Concepts of EBS
2. Environments vs Webservers
3. Demo1: Create a EBS Application, Environment, Deployment with Updation
4. Demo2: Do Demo1 with EB CLI

```
mkdir mydevenvironment
eb init
eb create
eb status
eb logs
eb health
eb config
eb deploy
```


### URLS: 
###### Load Balancers Types
https://docs.aws.amazon.com/AmazonECS/latest/developerguide/load-balancer-types.html
###### EB Getting Started
https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/GettingStarted.html
###### Sample App for reference
https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/samples/java-tomcat-v3.zip

-----



# AWS Elastic Bean Stalk Lab #2
#### Whats covered in this demo?
1. Basics of Load Balancers
2. Demo1: Load Balancer Demo
3. Demo2: Rolling Deployment via EBCLI
4. Demo3: Green Blue Deployments via EBCLI

Demo1:
1. Launch 4 EC2 instances accross 2 Availability Zones(Custom Security Group, VPC, Names)

1.1. Copy into User Text

/#!/bin/sh
yum -y install httpd php
chkconfig httpd on
/etc/init.d/httpd start
cd /var/www/html
wget https://s3-us-west-2.amazonaws.com/us-west-2-aws-training/awsu-spl/spl-03/scripts/examplefiles-elb.zip
unzip examplefiles-elb.zip

2. Create Application Load Balancers
3. Test Load Balancer URL (Check Load All Target)
4. Refresh Page multiple times
5. Shutdown A few instances
6. Refresh Again

Demo2: Rolling Deployment via EBCLI
1. EB init (orginal-lab)
2. eb create - One VPC, 2 instances, 
3. eb deploy
2. Change a file
3. eb deploy
4. check config with eb config
5. update health check url in eb config
6. eb create newEnv -c newEnv
7. Update index.php 
7. wait for newEnv
8. check Urls. 
9. Once Urls are up to date
 eb swap newEnv --destination_name oldEnv


