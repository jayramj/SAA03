# Route53 Basics

* R53 Hosted Zone is a DNS database for a domain
* It is globally resilient  
* Name Server records for a domain are entered in the top level hosted zone
* For a public zone R53 allocates 4 Name Servers. These name servers are accessible from public internet. They are also accessible from AWS VPCs using R53 resolver.
* R53 can be used to host zone files for externally registered domains
* Private Hosted Zone is not publicly accessible but only accessible to VPCs associated with the Private Hosted Zone
* In case of Split View, resource records associated with Public Zone are accessible publicly but associated with Private Zone are accessible only inside associated VPCs.
* In DNS records an A record maps name to an IP address. A CNAME maps a name to another name
* CNAMEs can not be used with a naked/apex domain name.
* R53 alias maps a name to an AWS resource. It can be used for apex domain as well as other records