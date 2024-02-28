- Place to store app logs in AWS. 
- ==Log Groups==: arbitrary name represent an application 
- ==Log stream==: instances within application/ log files / containers
- can define: log expiration policies (never, 1 day to 10 years)
- Can send logs to:
	- Amazon S3 (exports)
	- KDS
	- KDF
	- Lambda
	- OpenSearch
- Logs are encrypted by default
- Can setup own KMS based encryption

## Sources
- SDK, [[CloudWatch log agent]], CloudWatch Unified Agent
- Elastic Beanstalk: collection from app
- ECS: collection from container
- AWS Lambda: function logs 
- VPC Flow logs
- API Gateway
- CloudTrail based on filter 
- Route53: Log DNS queries

## CloudWatch Insights
- ==query cloudwatch logs for search and analysis==
- you can also see visualization
- result can be exported
- ==save query:== can be added to dashboard to run later
- purpose built query engine, ==not a real time engine== 
	- auto discovers fields from AWS services and JSON Logs events
	- Fetch desired event fields based on conditions

## Logs export to S3
- takes up to 12 hours to be available for export 
- API: CreateExportTask 
- ==Not real-time==, for real-time use Log Subscriptions

## Logs Subscriptions
- get ==real time== log events for processing or analysis 
- destination : ==KDS, KDF, Lambda==
- Subscription Filters for filtering - Upto 2 subscription filters per log group
![[Pasted image 20240130172702.png]]

How it works?
 - Cross account subscriptions 
	 - create a ==subscription filte==r in sender account 
	 - on destination account create a ==subscription destination==
		 - with ==destination access policy== : allowing sender account to put subscription filter 
	- Create an ==IAM role in destination account==, allowing access to put record in KDS. 
	- This IAM role ==can be assumed by ==CloudWatch Logs service in ==Sender account.==
## Metric Filters
- In a  Log group, For eg: we can add a metric filter which will track a custom metric. 
	- Like number of times our log has "installing"
- We can create an CloudWatch alarm on our metric Filter.

## CloudWatch Live Tail Feature
- tail logs as they are posted in cloudwatch logs
- 1 hour free every day