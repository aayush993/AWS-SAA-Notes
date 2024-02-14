
### What is a queue?
- Producer/s who send messages to the queue.
- Consumer/s who poll messages from the queue, who then process and delete messages from the queue.
- Queue is like buffer between your producer and consumer services.

Concepts:
1. [[SQS - Standard queue]]
2. [[SQS - Message Visibility Timeout]]
3. [[SQS - Long Polling]] 
4. [[SQS - FIFO Queues]]  
5. [[SQS - Delay Queues]]

## SQS Patterns
- Can set cloud watch alarm on cloud watch metric for queue length and scale our consumers. 
## SQS as buffer for database writes
- when writing directly to database in high traffic scenario, we may miss some writes.
- use SQS as buffer so that we don't loose any messages.
- this pattern can be used when client do not need any confirmation that write has happened.
- enqueue message in SQS using ASG
- de-queue message in SQS using ASG and write to database.

## SQS to decouple application tiers. 
- front end ASG
- Back end ASG 
- SQS buffer in between