# EC2 Basics

* EC2 is an AZ Resilient service
* EC2 instances can have multiple network interfaces in different subnets as long as they are in same AZ
* EBS runs inside a specific AZ
* An instance is tied to a host & if you restart an instance, it starts on same host
* The host changes either if the physical hardware of host fails or if the instance is stopped and then started.
* You can not connect network interfaces or EBS present in one AZ with instance in another AZ