# VPC Design

* VPCs are regionally isolated & regionally resilient service
* Its an isolated network with nothing allowed IN & OUT without explicit permissions
* While creating VPC one can select tenancy
    * Default tenancy means resources are on shared hardware.
    * With default tenancy, one can change it on per resource basis
    * Dedicated tenancy means resources are on dedicated hardware.
    * Once dedicated tenancy is used, it can't be changed back to default
* VPC has fully featured DNS provided by Route 53
* The DNS is available on IP Address = Base IP Address of VPC + 2
* Options in VPC related to DNS
    * enableDnsHostNames - gives instances DNS names
    * enableDnsSupport - enables DNS resolution in VPC