# Miscellanious Topics

## Instance Role

* Instance Profile is a wrapper around Instance Role.
* When you create an Instance Role in console , Instance Profile with same name is created automatically
* When you create an Instance Role from command line or CF , then Instance Profile needs to be created seperately
* When you attach an Instance Role from console UI to an EC2 instance, you are attaching an Instance Profile, which is attached to an Instance Role
* These security credentials are available in Instance metadat under iam/security-

## Systems Manager Parameter Store 
* Allows 3 types of parameters String,SringList, SecureString
* Supports Hierarchies of Parameters , Versioning of Parameters, Plain & Cipher Text parameters
* Changes to parameters can trigger events

## System & Application Logging

## EC2 Placement Groups

* Cluster Placement Groups
    * All instances are in same AZ, generally use the same rack & often the same host
    * Lowest Latency & Highest Packets per Second possible
    * Can span VPC peers but impacts performance significantly
    * 10 GPS single stream performance
* Spread Placement Groups
    * Spread across AZs & within each AZ different Rack
    * Maximum 7 instances per AZ
    * Provides Infrastructure Isolation
* Partition Placement Groups
    * Partitions are spread across AZs
    * Each partiton has different Rack. No shared rack between Partitions
    * Maximum 7 partitions are allowed in each AZ
    * You can target specific partitions for specific EC2 instances

## EC2 Dedicated Hosts
* Each host is for a specific family
* Entire host is dedicated for you hence there is no per instance charge
* RHEL, Suse & Windows AMIs are not supported
* Amazon RDS instances are not supported
* Placement groups are not supported
* They can be shared with other accounts in your ORG using RAM ( Resource Access Manager)

## Enhanced Networking
* Uses SR-IOV : Single Route IO Virtualization
* Higher I/O & Lower Host CPU utilization
* Higher Bandwidth

## EBS Optimized Instances
* Generally same network is used for EBS & Data
* With EBS Optimized , dedicated network capacity for EBS is provided