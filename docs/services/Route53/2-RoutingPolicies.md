# Routing Policies

## Simple Routing

* You can create 1 record per name
* Each record can have multiple values. E.g. An A record can map one name to multiple IPs.
* When client requests a name to be resolved, all values are returned in a random order.
* Simple routing does not support health checks

## Health Checks

* Health checks are performed by checkets located globally
* The checks are performed every 30seconds by default. Can be increased to every 10 seconds at a cost
* TCP, HTTP/HTTPS(200 checks), HTTP/HTTPS with String matching checks are supported
## Failover Routing

* A name has primary value and secondary value
* When a healthcheck fails on a resource, the client is routed to a secondary resource

## MultiValue Routing

* Create many records with same name. e.g. multible A records
* When querried by a client upto 8 records are returned
* Only healthy records are returned and those who fail healthchecks

## Weighted Routing

* This is used as simple load balancing or to test new versions of software
* Has many records with same name
* Each record has weightage assigned.
* Frequency record is returned is defined as record weight/total weight
* IF a record is unhealthy when selected, its skipped and selection again happens

## Latency Routing

* Used when trying to optimize for performance and user experience
* Multiple records defined for each name
* Along with the records, region for that record is specified
* One record for one name per region is allowed
* This does not account for local latency problems

## Geolocation Routing

* Location of users & location of resource is used to decide routing
* While creating records, they need to be tagged with location. Like Country, Continent, US States or Default
* The record matching happens in State,Countr,Continent order. Any record is matched, then that is returned.
* If no match happens , then default record is returned
* IF no match happens & default record is not defined, no record is returned.
* This does not return the "closest" record but only the applicable based on rule defined
* Useful for restricting content by location or provide language specific content

## GeoProximity Routing

* GeoProximity calculates the distance between the client & the resource
* For AWS resources, define its region. For other resources define latitude and longitude
* A Plus or a Minus bias can be defined. With a plus bias the distance that a resource can be increased while with minut it can be decreased