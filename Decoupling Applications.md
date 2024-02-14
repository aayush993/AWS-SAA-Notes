Two types of patterns for application communication:
1. Synchronous (app to app)
2. Asynchronous (app to queue to app)

Why Async or decoupled communication?
- Sync comms can cause sudden spike and overwhelm applications. 
- Decoupling then comes handy to avoid these outages. 
- by decoupling we can scale our applications independently and these decoupling tools can also scale independently.

Three managed AWS Proprietary models to decouple:
1. [[SQS]] :  queue model
2. [[SNS]]: pub/sub model
3. [[Kinesis]]: real-time streaming model

Then, we have [[Amazon MQ]]

## SNS + SQS Fan Out 
- If we send message to each SQS, if sending application fails in between or we add new SQS integration. 
- We use fanout to curb these.
- Send once to SNS and let all SQS subscribe to SNS.
- Advantage
	- SQS - Data persistence, delayed processing and retries
	- Add more SQS overtime
- Make sure SQS access policy allows SNS to write 
- Cross region delivery to SQS queues in other region
- [[SNS + SQS Fan Out Patterns]]

## Kinesis vs SQS Ordering - Revise this
Kinesis 
- You want to receive GPS data from 100 trucks. 
- You can use truck ID hashed and used as partition key
- same key will always go to same shard and hence to one consumer
SQS
- standard queue has no ordering
- FIFO will have order but will only send to one consumer. 
- If we scale consumers and don't utilize message group ID, second consumer have to wait until first batch is processed by first consumer
- If we use message group ID,
	- SQS will send messages belonging to one group to one batch if possible. 
	- If batch not full send last message from a group 
- This can result in message from one group ending up in one consumer. 
vs: 20 trucks, 5 Kinesis shards, 1 SQS FIFO
- 20 truck per shard
- data ordered in shards
- max parallel consumers : 5  - 1 per shard
- can receive upto 5MB/s data

- one queue
- 100 Group ID
- 100 consumers 
- 300 messages/ s or 3000 with batching

![[Pasted image 20240127001819.png]]

## Review Notes 
- KDS
	- ability for multiple apps to consume same stream concurrently 
	- consume in few hours delay 
	- consumers are limited to number of shards provisioned. 
- SQS
	- Scale transparently 
	- as many consumers 