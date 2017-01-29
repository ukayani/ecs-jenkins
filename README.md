# ECS Jenkins

A cloud formation template which runs Jenkins as an ECS service on an existing ECS Cluster.

This template depends on the creation of an ECS cluster using [ECSCluster](https://github.com/ukayani/ecs-cluster#ecsclustertemplate)
 
Once an ECS cluster has been created with the linked template, the stack name should be provided as input to this `ECSJenkins.template`

The ECS cluster should also be using an EFS mount [EFS Mount Template](https://github.com/ukayani/ecs-cluster#efswithmounttargettemplate)
 
## What is included
 
- Creation of a task/service to run Jenkins
- An ELB which fronts the Jenkins service, allowing communication on port 50000 (to do master/slave) and 80
- Jenkins instance is backed by an EFS volume to store Jenkins data
- Logging to CloudWatch for the Jenkins service 