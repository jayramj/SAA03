# Internet Gareway

* Regionally resilient i.e. One IGW per region is sufficient for all AZs within that region
* A VPC can have either 0 or 1 IGW. Similarly an IGW can belong to 0 or 1 VPC
* IGW is what allows services inside a VPC with public IPV4 address or IPV6 to be reached from Internet
* IGW is what allows to connect to AWS Public Zone or Internet
* Process of using IGW
    * Create IGW
    * Attach IGW to VPC
    * Create custom route table & associate with subnet that needs to be accessible from internet
    * Add default IPV4 and if required IPV6 default routes to RT with target being IGW
    * Configure subnets to allocate IPV4 public IP address & if required IPV6 addresses by default
* A public IPV4 address is never acutally physically assigned to the service they are being assigned to,
* Instead a record is created in IGW that map IPV4 private address with IPV4 public address. It is is IGW which does the translation between 2 when required
* E.g. IF an EC2 instance is allocated a public IPV4 address, inside the OS on that instance, the awareness of public IP address is not there.
* Hence Route Table with default route pointing to IGW, the mapping between Public & Private IP in IGW & IGW overwritting Private & Public IP address with each other when required is what makes Public IPV4 routing works