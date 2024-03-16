# Network Accesss Control Lists

* NACLs are associated with Subnets. NACLs are stateless.
* Every Subnet has an associated NACL. It filters data that crosses boundary of the Subnet
* Connections within the Subnet are not effected by NACLs
* NACLs are stateless i.e. they dont know whether traffic is a request or response. They only know whether it is inbound or outbound.
* The default NACLs in a a VPC have an impicity deny &  also an allow ALL rule. In effect NACLs allow all traffic by default hence default NACLs have no effect
* The custom NACLs though by default have one implicit deny rule for both inbound & outbound traffic. By default a custom NACL is not associated with any Subnet
* NACLs do not recognize any logical resources. They can be only assigned to Subnets
* NACLs are often used to explicitly deny traffic to bad IPs/Networks. 
* Generally Security Groups are used to allow traffic & NACLs to deny traffic
* A Subnet can have only one NACL associated either default or a custom one at any point of time
* Same NACL can be associated with multiple Subnets