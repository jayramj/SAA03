# ECS Basics

* ECS runs containers either in EC2 mode or Fargate mode
* A Task in ECS represents an application as a whole. So it can contain one or more container definitions
* Task Role defines an IAM role that the ECS task can assume to execute various operations
* ECS Service Definition tells how a task can be scaled in ECS
* Service how many copies of a task should run
* ECS Cluser runs within a VPC. So it can use all the AZs that the VPC spans