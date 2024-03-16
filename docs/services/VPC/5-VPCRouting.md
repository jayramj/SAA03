# VPC Routing

* VPC Router is present at N/W + 1 IP address by default. It is highly available & is present in all the AZs of your VPC
* Route table associated with each Subnet influences what VPC router does
* A Subnet by default uses main route table of the VPC. A Subnet can have only one route table associated at one time. Same route table can be used by multiple Subnets
* A route table decides what happens to traffic when it leaves a Subnet

## Internet Gateway
TBD

## Bastion Hosts
* Bastion Host = Jump Box
* Its an instance in a public subnet
* Used to allow incoming management connections
* Entry point for private only VPCs