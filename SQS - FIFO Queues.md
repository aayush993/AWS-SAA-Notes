- First in First Out
- ordering of messages in queue
- processed in order by consumer 
- Exactly once send capability ( by removing duplicates)
- limited throughput
	- Make sure we are in these ranges 
	- 300 msg/s without batching 
	- 3000 msg/s with 

- Name has to end with ".fifo"
- uses a message group ID and a deduplication ID for message.

## Transition FIFO Queue
1. Make sure of the limits. 
2. Cannot convert existing queue to FIFO

## Understanding FIFO Throughput
- 300 API calls per second 
- max 10 messages can be batched together. 
- we can decide how much message you need to send per API call.