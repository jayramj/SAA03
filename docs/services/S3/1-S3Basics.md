# S3 Basics

* S3 is private by default. Only the account root user has access to an S3 bucket by default
* One can be given access to S3 using Resource Policy
* Resource policies can allow or deny access to identities outside their own account vs identity policies which can give or deny access to identities only within their account
* Resource policies can give anonymous access
* ACLs are one more way of managing access to S3, but AWS does not recommend this

## Object Versioning

* Controlled at bucket level, starts of as disabled
* It can be enabled but once enabled it can not be disabled
* It can be suspended and then re-enabled
* When versioning of a bucket is disabled, id of that bucket is null
* When versioning is enabled, everytime a new version is uploaded, an object with new version is created
* S3 does not change the old version or its id but points to this new id as the current version
* If an object is accessed without mentioning id, its current version is returned

## Deletion of versioned objects
* If delete is requested of a versioned object without specifying a version, S3 simply adds a new special version of the object called delete marker. This simply hides the object
* If you delete , delete marker the deletion is undone
* When you delete an object by using id, that specified id only deleted
* When you delete the current version, immedite previous version becomes the current version
* All versions of the object occupy space & hence billed independently
* Even if versioning is disabled, all existing version continue to occupy space & hence billed

## Performance Optimization

### Single PUT upload
* This uploads using single stream of data
* S3 limits object size to 5GB for single PUT upload

### Multipart Upload
* Minimum upload size is 100MB
* Each upload can be split into max  10,000 parts
* Each part can range between 5 MB to 5 GB
* Each part even if it fails. can be reuploaded individually

### S3 Transfer Acceleration
* Uses network of Edge locations
* S3 bucket needs to be enabled for transfer acceleration
* Bucket name can not contain periods, needs to be dns compatible
* Data first gets uploaded to the nearest Edge location. Edge locations transfer data over AWS global network which is very fast


