# Elastic Network Interface

* Each EC2 instances comes with a default ENI attached to it
* You can add more ENIs to that instance each pointing to different Subnets but all of them have to be in same AZ as EC2
* Many things that appear to be attached to an EC2 instance are acutally attached to the ENI. Some examples - 
    * MAC Address
    * Primary IPV4 Private Address
    * 0 or more secondary private IP addresses
    * 0 or 1 Public IPV4 address
    * 1 elastic IP address per Private IP address
    * 0 or more IPV6 addresses
    * Security Groups
    * Source & Destination checks
* Secondary ENI have all capabilities are primary. Addtionally they can be detached from one instance & attached to other
* Secondary ENI + MAC = Licensing
* IPV4 Public ip addresses are dynamically allocated. It does not change when you restart an instance but changes when you stop & start the instance
* Public DNS resolves to primary private IPVs address inside VPC, everywhere else it resolves to public IP address
* When you assign an Elastic IP to an ENI, its public IPV4 address is removed and vice versa