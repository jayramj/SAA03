# Basics

* VPC is a virtual network created within an account & a region
* Default VPCs are created by AWS, one per region & come with specific configurations
* Custom VPCs by default is private & isolated from other VPCs, AWS public services as well as public internet
* VPC CIDR defines range of IP addresses that VPC occupiesis
* Default VPC CIDR is always 172.31.0.0/16
* A VPC is divided into Subnets. Each subnet is located in one AZ.
* The AZ of Subnet is defined at time of creation & can never be changed
* Default VPC has 1 subnet in each AZ. The CIDR

## Points about Default VPC
* One per region , can be removed & recreated.
* While one can delete default VPC from a region, certain AWS services assume presence of Default VPC. Hence its best to have one even if you dont use it.
* A default VPC has a /16 CIDR while each subnet has /20 CIDR
* Default VPC comes pre configured with an Internet Gateway, Security Group & NACL
* Anything that is provisioned in any subnet in default VPC, subnets assign it a public IPv4 address. This is unique to default VPC