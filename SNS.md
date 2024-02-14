- send one message to many receivers
	- Direct integration for each new receiver 
	- Pub/Sub - send it to a topic all receiver subscribe to that

- SNS - Simple Notification Service
- event producer sends to one SNS topic 
- event receivers(subscriptions) - to that SNS topic 
- Each subscriber get all message ( optionally filtered message)

## Subscribers - remember these while going in exam
1. Emails, SMS or push notifications, HTTPs endpoints
2. SQS, Lambda or Kinesis Data Firehose

## Producers
- Many AWS services 
- Any notification happens in AWS, these services send a notification to a specified topic

## To Publish
1. Topic publish (using SDK)
	1. create topic 
	2. create subscription (or many)
	3. Publish to the topic 
2. Direct Publish (for mobile apps SDK)
	1. Create platform application 
	2. create platform endpoint
	3. Publish to platform endpoint
	4. Google GCM, Apple APNS, Amazon ADM

## Security 
Exactly Similar to [[SQS - Standard queue]] 

## SNS - FIFO topic 
- similar features as SQS 
	- Ordering by message group ID
	- deduplication using deduplication ID
- Use: if we need to use FIFO(ordering + deduplication) [[SNS + SQS Fan Out Patterns]]
- both standard and FIFO SQS can subscribe to this
- Limited throughput 

## Message Filtering 
- JSON policy to filter messages sent to topic's subscriptions
- if subscription has no filter policy, all messages.