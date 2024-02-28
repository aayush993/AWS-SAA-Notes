- Events are anything like create, remove, restore or replicate an S3 object 
- For eg: for every object with *.jpg* in name generate an event. 
- We can use that to generate thumbnails for those objects.
- ==Can create as many S3 events as desired.==
- Can ==send to SNS, SQS(No FIFO), Lambda== 
- Can be delivered within seconds or sometime a minute or longer. 

#### Event Notifications - IAM permissions 
1. SNS - SNS Resource Access Policy 
2. SQS - SQS Resource Access Policy 
3. Lambda - Lambda Resource Policy

#### S3 Event Notifications with [[Amazon EventBridge]]
- ==All events end up in Eventbridge== 
- from there we can ==set rules to send them to 18+ AWS services ==as targets
- Advanced filtering - with JSON rules (metadata, object size, name...)
- Multiple destinations- ex: step functions, kinesis streams/firehose
- Eventbridge capabilities - archive, replay events and reliable delivery.