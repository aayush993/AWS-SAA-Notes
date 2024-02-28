## Incorrect
- [[S3 Object Encryption]]
	- Customer managed encryption- client side 
	- Customer managed key - SSE-C
- [[S3 Static Website Hosting]]
- [[Amazon Transcribe]] vs Amazon Alexa
	- Transcribe is an ASR service.
	- Alexa - general purpose voice interaction
	- Lex - creating custom conversational interfaces
- [[ElastiCache]] Redis vs Memcached
	- Redis for geospatial data, sorted sets and many other HA features and transactional support 
	- Memcached for multi threaded architecture.
- Message sent one by one at a high rate: KDS
	- batching can solve without extra costs.
	- adding more capacity can help but that will increase cost.
- S3 event notification supports only Standard SQS.
- S3 Objects metadata is not encrypted.
- For session management DynamoDB vs Redis
	- Use Elasticache redis as it is the popular choice because of its fast performance and Data structure capabilities. 
	- DynamoDB can be a choice when you need something fully managed and integrated with AWS services particularly.
- Cross region Automated backup for RDS.
- By default dynamodb tables encrypted with AWS owned key hence no CloudTrail
- DTO on direct connect is lower than internet and charged per GB data sent out. 

## Doubts
- Link-Local addresses
	- Non routable IP addressed
	- EC2 uses addresses from this space to provide services accessible only from EC2 Instance. Services running on EC2 underlying host.
- Retrieve user-data and meta-data from within EC2 Instance using URIs. 
	![[Pasted image 20240218213115.png]]
- AWS tasks only  root account user can do:
	- change account name or root password or root email address
	- change AWS support plan
	- close AWS account
	- enable AWS Multi-Factor Authentication (AWS MFA) on S3 bucket delete
	- create Cloudfront key pair
	- register for GovCloud.
- Kinesis vs SQS - KDS for streaming/real-time data