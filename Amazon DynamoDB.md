- Fully managed, Highly Available with replication across multiple AZ's 
- NoSQL DB-==with transactional support==
- Scales to massive workloads, distributed database
- Millions of req per second, trillions of rows, 100S OF TB storage 
- Fast  and consistent in performance 
- IAM integration for security 
- Low cost and auto scaling 
- No maintenance, ==DB is already there just create your tables.== 
- ==Standard and IA table class==

- It is made of tables 
- Each table has primary key 
- Each table can have infinite items 
- ==Evolving schemas: ==Each item has attribute (can be added over time)
- Max item size - 400KB
- Data types supported:
	- Scalar - string, boolean, binary, number, null
	- Document types - list, Map
	- Set Types - String, Number or Binary Set

Record = Primary Key (Partition key + optional sort key) + attributes
## Read/Write Capacity Modes
- Table's capacity - Read/write throughput 
- Provisioned mode (default)
	- Specify no of read write / second 
	- Capacity plan required
	- Pay for ==provisioned== Read Capacity Unit and WCU
	- Possibility to add **==Auto-scaling==** for RCU and WCU
- On-Demand mode
	- No cap plan required
	- Read/ write scales up and down auto 
	- Pay for each read write, more costly 
	- ==For un-predictable workloads, steep sudden spikes==

## Advanced Features
1. [[DynamoDB Accelerator DAX]]
2. [[DynamoDB - Stream Processing]]
3. [[DynamoDB - Global Tables]]
4. [[DynamoDB - TTL]]
5. [[DynamoDB - Backups for DR]]
6. [[DynamoDB - Integration with S3]] 

By Default tables are encrypted by AWS owned keys. 
You can choose to encrypt with managed or customer managed keys.