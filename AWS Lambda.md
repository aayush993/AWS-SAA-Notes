- Virtual functions - no servers to manage unlike EC2 
- Limited by time - ==15 mins short executions== 
- Run on-demand (unlike EC2 instances, even if we are not using they have to be running)
- Scaling is automated
- [[Bound to Region]] 

## Benefits 
- Easy Pricing 
	- Pay per request and compute time 
	- Free tier- 1000000 Requests and 400000 GBs of compute time.
- Integrated with the whole AWS suite 
- Many programming language support 
- Easy monitor - Cloudwatch 
- Easy to get more resources per function (==up to 10 GB== of RAM)
- ==Increasing RAM increase CPU and network performance==

## Language Support 
- Node.js 
- Python 
- Java (Java 8 support )
- C# (.net core)
- Golang 
- C#/ Powershell
- Ruby 
- ==Custom Runtime API== (community supported, ex: Rust)
- Lambda Container Image 
	- image should implement ==Lambda Runtime API== 
	- ECS-Fargate is preferred for running arbitrary Docker images.

## Lambda AWS Integrations Mains
1. [[API Gateway]]: To create rest api to invoke our lambda functions 
2. Kinesis: Do some data transformation on the fly 
3. [[Amazon DynamoDB]] : Create some triggers, something happens lambda triggers
4. [[S3]] : Same triggers
5. CloudFront : [[Lamda@Edge]]
6. CloudWatch : 
	1. [[Amazon EventBridge]] : Some state changes and we want to do some automations.
	2. [[CloudWatch Logs]]: To stream the logs 
7. SNS, SQS: To process messages 
8. [[AWS Cognito]]: Whenever a user logins

Concepts:
1. [[Lambda Example Architectures]]
2. [[Lambda Limits]]
3. [[Lambda Snapstart]]
4. [[Edge Functions]]
5. [[Lambda in VPC]]
6. [[RDS - Invoke Lambda & Event Notifications]]: RDS Data events and DB Instance Events
## Lambda Pricing  
- Very cheap hence very popular 
- Pay per calls
	- First million calls free
	- after that ==0.20 $ per million== 
- Pay per duration (increment of 1ms)
	- 400,000 GB-second compute time free per month- if free
	- for 1GB we get 400,000 seconds 
	- after that ==$1 for 600,000 seconds==.


## Review Notes 
- Lambda best practices
	- Enable VPC - only if required. Once enabled it is subjected to VPC rules 
		- and uses NAT to interact with public APIs 
	- Deploy common code in Lambda Layers
		- a function can have max 5 layers at a time 
		- Layers have resource based policy for cross-account or org permissions 
		- Total unzipped size with all layers cannot be more than 250 MB
	- Watch total package size - start will be slow 
	- Monitor concurrency using cloudwatch alarms ""ConcurrentExecutions"
		- to avoid surprise in bill
	- Over provisioning memory but cautiously.
