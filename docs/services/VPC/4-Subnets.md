# Subnets

## Basics
* In Diagrams Blue - Private Subnets, Green - Public Subnets
* Subnet is a part of a VPC created in one AZ. This assigned AZ can not be changed
* Subnet CIDR has to be within the VPC CIDR range
* A Subnet's CIDR can not overlap with CIDR of other Subnet within the VPC
* A Subnet can be optionally allocated an IPV6 CIDR which is a /64 CIDR
* Subnets by default can communicate with other Subnets in the same VPC
* 5 IP addresses with a Subnet are reserved
    * First address of any Subnet represents the network
    * N/W + 1 address is used by VPC router
    * N/W + 2 is for DNS
    * N/W + 3 not used. Reserved for future use
    * Last IP address of every Subnet is reserved as Broadcast Address
* Subnet has options to Auto Assign IPV4 public addresses and IPV6 addresses