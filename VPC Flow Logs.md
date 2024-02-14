- Capture information about IP traffic going into interfaces:
	- VPC Flow Logs 
	- Subnet Flow Logs 
	- ENI Flow Logs
- Monitor network connectivity issues 
- Can be send to 
	- S3
	- CloudWatch Logs
	- KDF in same or diff account
- Capture network info from AWS managed interfaces also like : RDS, ElastiCache, Redshift etc...

## Flow Logs Syntax
- Metadata about network packets going into your VPC. 
- Info we can analyze 
	- srcaddr & dstaddr - identify problematic IP 
	- srcport & dstport - for port issues 
	- Action - Succes or failure due to sec group / NACL
	- Can be used 
		- Analytics
		- malicious behavior 
	- Query VPC Flow Logs 
		- Athena on S3 
		- Cloudwatch logs insights
- ![[Pasted image 20240205125734.png]]

## Troubleshoot NACL & Sec G issues
- Look at Action in VPC Flow Logs
- Incoming 
	- Inbound reject - can be NACL or Sec group 
	- outbound can only be NACL
- Outgoing 
	- Outbound can be NACL or sec group
	- Inbound NACL only
![[Pasted image 20240205130105.png]]


## Sending Logs 
1. Send to S3 bucket, create a Flow log and a bucket. ==select the bucket it will attach a resource based policy== to allow access to the bucket 
2. Send to CW logs, need to ==create CW Log group and IAM role to be assumed by vpc-flow-logs== 
	1. Create IAM role with custom policy. Give CW logs full access. 
	2. Create a Log Group in CW Logs. 

CloudWatch Logs for doing some metric alarm system 
Athena and S3 for some Query analysis. 
