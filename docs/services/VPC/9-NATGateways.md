# NAT Gateways

* NAT - Network Address Translation
* IGW is example of a static NAT
* IP Masquarading - This is a type of NAT where by a CIDR block is hidden behind a single IP address
* IP Masquarading gives a bunch of Private IP addresses outgoing internet access
* Private devices that use can initiate outbound internet connections, can receive responses but they can not receive inbound network connections
* NAT Gateway needs a public IPV4 address. Hence it runs in a public Subnet.It uses Elastic IPs.
* It is not a Regionally resilient service. They are AZ resilient Service. For full regional resilience, 1 NAT Gateway needs to be provisioned in each AZ aldon with a Route Table per AZ.
* NAT Gateways are a managed service. They have both an hourly fixed charge as well as data transfer charges
* NAT instance can be significantly cheaper at high volumes of data.
* One can use NAT Instances as Bastion hosts or for port fowarding
* NAT Gateays dont support Security Groups. You can only use NACLs. But with NAT instances you can use both
* NAT is not required for IPV6 as in AWS all IPV6 addresses are publicly routable.