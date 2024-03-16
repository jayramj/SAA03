# Security Groups

* Security Groups are stateful. If a request is allowed corresponding response is automatically allowed
* Security Groups do not have an explicit Deny
* Cant be used to block a specific bad actor. Which is where NACLs will come into picture
* Seccurity Groups are not attached to instances or to Subnets. They are attached to Elastic Network Interfaces (ENIs)
* Security Groups can refer to logical resources
* When you reference a SG(SG1) from any other SG(SG2), you are actually referencing any resources that are associated with SG1.
* Logical references allow self referencing