# S3 Object Storage Classes

## S3 Stanard
* This is the default storage class. This is also most balanced class
* The objects are by default stored across 3 availability zones. This provides 11 9s of durability
* Billing
    * GB/month storage fee
    * $/GB for data transfer out
    * No charge for data transfer in
    * Charge per 1000 requests
* Data access is immediately, with 1st byte response in milliseconds

## S3 Stanard IA (Infrequent Access)
* Data replication is same as Stanard i.e. 3 AZ
* Latency is same
* Storage costs are much more cheaper ( nearly 50% cheaper)
* It has retrieval fee per GB in addition to data transfer fee
* However long you store objects, minimum billed duration is 30 days
* Minimum billed size is 128kb irrespective of how small object is
* Dont use it for short lived objects or very frequently accessed objects or very small objects

## S3 One Zone IA
* Retrieval fee, minimum storage duration & minimum 128 kb size are all same as Stanard IA
* Data is stored in only 1 AZ. No replication
* Use for Long lived infrequently access but easily replaced data. 

## S3 Glacier Instant
* Access to data is instant
* Minimum storage duration charge of 90 days
* Data replicated in 3 AZ

## S3 Glacier Flexible Retrieval
* Storage cost is about 1/6th of S3 Standard
* 40 Kb minimum retrieval size & 90 days minimum billable duration
* Objects aren't instantly available. Hence they cant be made public
* To retrieve objects a special job needs to be run
* When objects are retrieved they are stored temporarily in S3 Standard IA class
* Retrieval jobs are of 3 types
    * Expedieted - Data becomes available in 1 to 5 minutes. Most expensive
    * Standard - Data becomes available in 3 to 5 hours. Cheaper
    * Bulk - Data becomes available in 5 to 12 hours. Cheapest

## S3 Glacier Deep Archive
* Cheapest class for storage
* Objects have 40 kb minumum billable size & 180 days minumum billable duration
* Standard retrieval jobs take 12 hours & bulk jobs take upto 48 hours

## S3 Intelligent Tiering
* Consists of 5 tiers - Frequent Access ,Infrequent Access, Archive Instant Access, Archive Access, Deep Archive
* Object access is monitored & is moved between tiers automatically
* Frequently accessed objects are in frequent access tier
* If not accessed for 30 days - Infrequent Access
* If not accessed for 90 days - Archive Instant
* 90 - 270 days - Archive Access
* 180 to 730 days - Deep Archive
* Instead of retrieval cost there is monitoring & automation cost per 1000 objects