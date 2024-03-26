# EC2 Purchase Options

* On Demand
* Spot
* Reserved
    * Scheduled Reserved Instances
* Dedicated Hosts
* Dedicated Instances
* Capacity Reservations - Following priority is followed to meet committments
    * Reserved Capacity
    * On Demand
    * Spot
* Regional reservations provide billing discount but dont reserve capacity. In terms of priority it competes with On Demand instances
* Zonal reservations provide both billing discount as well as reserve capacity. But this is limited to AZ
* On Demand Capacity Reservations entails no billing discount but they gurantee capacity. Any unused capacity is billed irrespective.
* Savings plan - This is hourly spend committment irrespective of instance type
* Savings plan can be for general compute ( e.g. EC2, Lambda, Fargate) or EC2 savings plan