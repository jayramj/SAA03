# EC2 Basics

* EC2 is an AZ Resilient service
* EC2 instances can have multiple network interfaces in different subnets as long as they are in same AZ
* EBS runs inside a specific AZ
* An instance is tied to a host & if you restart an instance, it starts on same host
* The host changes either if the physical hardware of host fails or if the instance is stopped and then started.
* You can not connect network interfaces or EBS present in one AZ with instance in another AZ
* Every instance has 2 status checks
    * System Status - Issues impacting either EC2 service or the Host
    * Instance Status - Problems with specific instance
* Instance Metadata - http://169.254.169.255/latest/meta-data. Following metadata is available
    * Environment
    * Netowrking
    * Authentication
    * User Data
* Metadata service itself is not authenticated or encrypted
* Userdata url is - http://169.254.169.254/latest/user-data. 
* Userdata can be 16kb max
* Userdata can be consumed once i.e. at time of launch
* cfn-init is helper script used for EC2 initialization
* cfn-init is invoked from user data
* cfn-init works with stack updates i.e. it observes instance meta data. When the meta data changes cfn-init can take actions
* Creation Policy - It is added to a logical resource (e.g EC2Instance) in a CF template. The ResourceSignal attribute in the logical resource is used to make the Resource send a signal to CF.
* cfn-signal command reports success or failure of cfn-init.