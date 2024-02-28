To point hostname to hostname we have CNAME. 
But we cannot use root domain there. like example.com

Alias Records
- Points a hostname to an AWS Resource
- ==Works for root domain as well.== 
- Free of charge 
- Native health check. 
- can't set TTL 
- Always type A/AAA

Automatically recognized changes in resource IP's. It's an extension of DNS functionality.

#### Targets can be:
ELB, CloudFront, API Gateway, Elastic Beanstalk Environments, S3 Websites, VPC Interface Endpoints. Global accelerator, ==Route 53 record in same hosted zone==.
#### Cannot be set for EC2 DNS Name


## Review Notes 
--- 
- Diff in CNAME and Alias records
	- Can redirect queries to 
		- Alias - CloudFront, S3, Another record in same Route 53 hosted zone
			- redirect to a query to a record in the example.com hosted zone in Route 53
		- CNAME 
			- redirect DNS Queries to any DNS record. (Even outside Route 53)
			- No need to use Route 53 as DNS service for domain you are routing to.
	- Zone Apex
		- can create alias record for same name as hosted zone.
		- Exception - Alias record redirecting to a record in same hosted zone that has type of CNAME record (CNAME record for zone apex is not supported)
		- Alias record must have same type as the record you are targettin.
	- Cost 
		- Alias Free
		- CNAME charged