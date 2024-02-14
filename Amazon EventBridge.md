- Used to be called CloudWatch Events 
- We can do three things 
	- Schedule: Cron jobs (Scheduled scripts)
		- every hour send event to Lambda to trigger script
	- Event Pattern: Event rules to react to service doing something 
		- eg: rule to send email on every login event 
	- Trigger Lambda functions, to SQS or SNS 

## Sources of Events to EventBridge 
- EC2 Instance : eg: start instance 
- CodeBuild: eg: failed build 
- S3 Event 
- Trusted Advisor
- CloudTrail 
- Scheduled or Cron
We can also filter the events from sources. 
==Each event generates a JSON file with lots of details.== 

## Destinations 
For Eg:
1. Compute : Lambda, AWS Batch, ECS Task 
2. Integration: SNS, SQS, KDS
3. Orchestration: Step function, CodePipeline, CodeBuild 
4. Maintenance: SSM, EC2 Actions 

## Event Bus Capability
- Default Event Bus - Event bridge is default for all AWS services 
- Partner Event Bus
	- Like: Zendesk, DataDog etc. 
	- You can react to their events in your account 
- Custom Event Bus:
	- For you applications to send. 
	- All EventBridge capabilities

## Archive Events - all or filter - indefinitely or set period
## Replay archived events eg: for testing, debugging 

## Schema Registry
- EventBridge infer schema for your events.
- You can download code bindings
	- Schema registry generate code for your application to know how data is structured in event bus.
- Schema can be versioned.

## Resource-Based Policy 
- Manage permissions for an event bus
- Ex: Allow or deny== cross account or region access==
- Use: ==aggregate all events from your AWS organization== in a single AWS account or region

## Sandbox 
- we have this feature to test our Event patterns without a Rule
- we can have a pattern to match event. 
- if matched we can do something with it or send it somewhere