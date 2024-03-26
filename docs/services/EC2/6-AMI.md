# Amazon Machine Image

* AMIs are regional. It has unique id in every region. It can be only used in the region it is available
* Whenever you create an Image (i.e AMI) from an existing EC2 instances, the device id as well as snapshot of current data of all the attached devices i.e. both boot as well as data devices is copied in that Image
* Whenever you create and instance from the above image, it will get the exactly same image ids as well as data as was present when Image was created.
* AMI Baking - Create an AMI from a configured instance along with applications installed on it
* AMI once created can't be edited/updated
* AMI billing includes billing for EBS snapshots
* By default AMI is private i.e. can be only accessed by Account that created it