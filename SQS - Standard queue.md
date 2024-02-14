- Oldest offering
- Fully managed service to ==decouple applications==
- Attributes
	- ==Unlimited throughput and unlimited number of messages in queue==
	- Short lived messages: (default 4 days to 14 days)
	- Low latency (<10 ms for publish and receive)
	- Limitation of 256KB message sent.
- ==At least once delivery==, occasionally duplicate messages.
- ==Best effort ordering==, can have out of order messages.

### Producing messages
- Produced using SDK (SendMessage API)
- message is persisted in SQS until consumer deletes it. 

### Consuming messages
- consumers can be running on EC2 instances, servers or AWS Lambda
- Poll for messages - r==eceive up to 10 messages at a time.==
- Process the message 
- Delete the message - DeleteMessage API

### Multiple consumers
- Consumers receive and process in parallel. 
- At least once delivery
- Best effort ordering 
- consumer has to delete message after processing them 
- Improve throughput: by horizontal scaling consumers. "Very Common integration"
	- Use ASG on EC2 consumers. 
	- Setup cloud watch alarm on cloudwatch metric ApproximateNumberOfMessages (Queue length)
	- if breached scale the ASG

### Decouple application tiers using SQS
- instead having one front end, to take requests and process it, 
- We can have one front end tier to receive requests and send them to SQS.
- We can have a backend tier to process requests. 
- We can scale both tiers independently and use different kind of EC2 instances depending on use case. 
- meanwhile SQS has unlimited throughput and very robust. we don't have to worry about that failing.

### Security 
1. Encryption 
	1. In flight - HTTPS API 
	2. At -rest - KMS 
	3. Client side encryption - there is no out of the box support. client can do itself. 
2. Access controls- IAM policies to regulate access to SQS API
3. SQS Access Policies ( similar to S3 bucket policies)
	1. cross account access 
	2. allowing other services like SNS or S3 to write to SQS