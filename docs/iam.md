# IAM

## ARN - Amazon Resource Name

ARN Formats 

* arn:partition:service:region:account-id:resource-id
* arn:partition:service:region:account-id:resource-type/resource-id
* arn:partition:service:region:account-id:resource-type:resource-id
* e.g arn:aws:s3:::catgifs


## Basic

* Only 5000 IAM users are allowed per account
* IAM users can be part of max 10 groups only
* IAM Groups can not be referred in resource policieis as they are not real identities
* Each account has default 300 limit for number of groups

## IAM Roles
* Trust Policies - They control which identity can assume a role
* STS generates temporary security credentials when a Principal assumes a role based on Trust Policy
* Whenever a service needs to assume a role it invokes sts::AssumeRole operation
* When should you use roles?
    * Existing identities or more than 5000 identities need to be supported
    * When using identity federation
    * Giving access to identities from other AWS accounts
* A service linked role 
    * is an IAM role directly linked to a specific service
    * Predefined by the services
    * Might be created by the service itself
    * Service might allow you to create the role
    * Service linked role can not be deleted unless it is being used in the service
    * If you want to give an identity ability to use a service linked role but not create & update it, then it needs to have "iam:PassRole" permission

## AWS Organizations
* An aws account when created by default is a standard account not part of any organization
* An AWS account can create an AWS Organization
* The account thats creates the organization becomes Management Account or Master Account OR Payer Account for the organization
* Reservations & Volume discounts are consolidated at Organization level
* When a standard account joins an AWS Organization, it becomes a Member Account & stops being a standard account
* At top of Organizational Tree, there is a Organizational Root which is a container for other containers or other accounts
* The containers other that Organization Root are called as Organizational Unit or OU

## Service Control Policies (SCP)
* Management Account is never affected by SCP even if there is one attached to it
* SCPs are account permissions boundaries
* They limit what an account can do
* While an Account Root User can do everything in an Account, with SCP if a restriction is placed on an Account, Root User will have full control within those restrictions
* SCP's can operate either as Allow List or a Deny List. The deny is a deny list
* When SCP are enabled, the default policy called "Full AWS Access". i.e. in default implementation, nothing is restricted
* Implementing Allow Lists involves disabling default FullAWSAccess. Then add services which you want to be enabled.