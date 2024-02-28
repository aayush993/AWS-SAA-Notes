
## DB Types
1. RDBMS - SQL /OLTP - for joins
	1. [[RDS]]
	2. [[Aurora]]
2. NoSQL DB - not for joins
	1. [[Amazon DynamoDB]]: JSON
		1. can replace elasticache as a KV store
		2. Eg: storing session data using TTL feature
		3. Use: Small documents, Serverless cache
	2. [[ElastiCache]] : KV pairs
	3. [[Amazon Neptune]] : graphs
	4. [[DocumentDB]]: mongoDB
	5. [[Keyspaces for apache cassandra]] : Serverless
3. Object Store :
	1. [[S3]] and Glacier
		1. Great for storing big objects, not for many small objects
		2. static files, web hosting
4. Data warehouse: SQL Analytics and BI 
	1. [[Redshift]] : OLAP
	2. [[Amazon Athena]] - serverless SQL query service
	3. [[Amazon EMR]] - Hadoop clusters for big data processing.
5. Search:
	1. [[Amazon OpenSearch]] : JSON
6. Graph : Neptune: relationships 
7. Ledger : [[Amazon Quantum Ledger DB]] : Serverless
8. [[Amazon Time Stream]] : Serverless for time series