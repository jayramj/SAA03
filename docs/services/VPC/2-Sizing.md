# Sizing & Structure

* A smallest VPC can be /28 i.e. 16 IP network & largest VPC can be /16 i.e. 65536 IP network
* Each time the prefix is increased by n, it creastes 2^n networks. 
    * /16 + 1 = /17. Hence networks = 2^1 = 2
    * /16 + 2 = /18. Hence networks = 2^2 = 4
    * /16 + 4 = /20. Hence networks = 2^4 = 16