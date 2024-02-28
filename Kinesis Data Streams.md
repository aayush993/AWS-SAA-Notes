- Kinesis Data stream is used to ingest big data. 
- Stream is divided into shards (1-n)
- capacity of stream depends on shards provisioned
- we can scale by increasing shards.

### Producers
- Any applications, clients ==leveraging SDK and KPL== 
- Any servers with ==kinesis agent==

- Producers send a "record" to data streams. 
- A ==record consists of Partition key + data blob.==
- Partition key decide to which shard record will go. 
- 1 MB/sec or 1000 msg per sec per shard. 

### Consumers
 Consumers: 
	- Write own: KCL, SDK
	- ==Managed: Lambda, KDF, KDA==

- when it receives a record, it has 
	- partition key 
	- seq no: where the record was in the shard
	- Data blob
- Consumption modes:
	- Shared: 2 MB/sec per shard all consumers share that
	- Enhanced: 2MB/sec per shard per consumer

### Notes
- ==Retention==: 1 to 365 days
- ==replay==: Ability to Reprocess data 
- ==Immutability==: once data inserted in kinesis, can't be deleted
- ==Ordering==: data with same partition goes to same shard
- Producers use: SDK, KPL, Kinesis Agent
- Consumers: 
	- Write own: KCL, SDK
	- Managed: Lambda, KDF, KDA

### Capacity Modes
1. Provision mode  (if you can plan capacity)
	1. choose no. of shards, scale manually or using API 
	2. Each shard gets in 1 MB/sec or 1000 msg per sec per shard. 
	3. gets out  2 MB/sec per shard (classic or enhanced fan out consumer)
	4. Pay per shard provisioned per hour
2. On-Demand mode
	1. no need to provision or manage capacity 
	2. default capacity provisioned ( 4mb/sec in or 4000 records per second)
	3. scales auto based on observed throughput peak during last 30 days
	4. Pay per stream per hour & data in / out per GB

### Security
1. Control access: IAM policies
2. Encryption
	1. In flight: HTTPS endpoints
	2. at rest: KMS 
3. Can implement your own client side encryption/decryption (harder)
4. VPC endpoints for access within VPC
5. Monitor with CloudTrail

## How to Use
- Create a stream. 
- By Using SDK We can use low level API
- Like --put-record
- then --describe-stream
- then use shard Id, to get shard iterator
- Using shard iterator get the messages and next shard iterator.



- To reduce overhead and increase throughput, the application must batch records and implement parallel HTTP requests.