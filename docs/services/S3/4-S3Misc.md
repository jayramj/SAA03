# Miscallaneous

## S3 Lifecycle Configuration
* For lifecycle transition an object in S3 Standard has to be there for duration of 30 days before it can be moved to other storage classes using a transition rule
* One can manually move the object to other classes at any point of time

### Transition Actions
### Expiration Actions

## S3 Replication

### SRR
* Both the source & destination buckets are in the same region

### CRR
* Source & Destination buckets are in different regions

### Common configurations
* Replication configuration is applied to source bucket
* Configuration consists of a destination bucket & an IAM role that is used to perform replication
* IAM role's Trust policy allows it to be assumed by  S3 service
* Role' permission policy allows it to read from source bucket & replicate into destination bucket
* In case of different aws account replication, the IAM role is by default not trusted by the destination S3 , since its in a different account.Hence a bucket policy is added to destionation bucket that allows this IAM role permissions to write or replicate into the destination bucket
* The default configurations replicate all objects, the storage class is same as source bucket & the owner is the source account. That means the destination account by default can not access replicated bucket
* By default replication is not retroactive i.e. it replicates all objects that point onwards. Deletes are not replicated by default
* Versioning has to be ON for both source & destination bucket for replication to work
* RTC(Replication Time Control) provides guranteed 15 minutes replication SLA
* System events or LifeCycle Events, Glacier or Glacier Deep Archive are not replicated

## S3 Select & Select Glacier
* You can create SQL like statements to select part of an object
* This can operate on csv,json,parquet, bzip2 compressed csv or json

## S3 Event Notification
* When configured, notifications are generated when events occur in a bucket
* The destinations could be SNS,SQS or a Lambda function

## S3 Access logs

## S3 Object Lock
* Can be enabled on new buckets. In order to enable it on existing buckets, need to contact aws support
* Any bucket with Object lock enabled also has versioning enabled
* Write Once Read Many i.e. No Deletes or Overwrite allowed
* An object can have Retention Period & Legal Hold

### Retention Period Object Lock
* Specify retention period in days or years while creating object lock
* If retention period is applied using compliance mode , object verion can not be adjusted, deleted or overwritten during the retention period. Also retention period can not be reduced or retention mode can not be changed during retention period
* Governance mode - Here special permissions can be granted to special identities to adjust lock settings
* s3:BypassGovernanceRetention permission as well as x-amz-bypass-governance-retention:true header are required to adjust lock settings

### Legal Hold Object Lock
* Can be set ON or OFF on object version
* Prevent accidental  deletion or actually put a legal hold 

## S3 Access Points
* Access points allow to split an S3 bucket into smaller units
* Different access points can have different policies for access control
* Each access point can have different network access controls
* Each access point as different endpoint accesss