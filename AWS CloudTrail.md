- Provided governance, ==compliance and audit ==for your AWS account 
- enabled by default 
- Gives history of events and API calls made by AWS account. 
- ==Put logs== 
	- CloudWatch Logs 
	- S3
- Trail can be applied 
	- to all regions (default)
	- single region 
- Always investigate CloudTrail, if something happens to a resource. 

## CloudTrail Events
- Management Events : Default trails are configured to log
	- Operations performed on resources in your AWS accounts 
	- Ex: Attach IAM policy, Createsubnet
	- ==Can separate Read and write Events==
- Data Events :  by default are not logged
	- ex: GetObject in S3 or CreateObject, InvokeAPI in Lambda
	- Can separate Read and write Events
- CloudTrail Insights Events
	- ==Has to be enabled and paid for==
	- It ==detects unusual activity== in your account 
		- inaccurate resource provisioning 
		- Burst of AWS Iam actions
		- Gaps in maintenance 
	- analyzes normal management events to ==create baseline== 
	- and then analyzes continuously  write events to ==detect unusual patterns==.
		- create insight events
	- Appear in CloudTrail Console, Can send them to , ==S3 bucket, EventBridge event==

## CloudTrail Events Retention 
![[Pasted image 20240130192718.png]]

## EventBridge Integration
- For eg: we delete something in DynamoDB 
- that API call is logged in Cloudtrail 
- That generates and event which ends up in EventBridge
- for which we can create a rule to alert SNS topic. 

![[Pasted image 20240130193133.png]]

