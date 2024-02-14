- Serverless SQL query service for data in S3
- Built on Presto engine
- Supports 
	- CSV
	- JSON
	- Avro
	- Parquet
- Price: 5$ per TB scanned
- Commonly used with Amazon QuickSight for dashboards and reports
- Use case: 
	- BI
	- Analytics
	- reporting
	- analyze and query VPC flow logs, cloudtrail logs etc..

> Analyze S3 data using serverless SQL > Athena


## Performance Improvement
- Use ==COLUMNAR DATA== for cost savings (less-scan)
	- Apache Parquet or ORC recommended
	- Huge perf improvement
	- Use Glue to convert format to these 
- ==Compress Data==  for smaller retrievals 
- Partition datasets in S3 for easy retrievals in virtual columns 
- ![[Pasted image 20240129145616.png]]
- Use Larger files > 128 MB to minimize overhead 

## Federated Query
- Run SQL query on data in any 
	- relational 
	- non relational
	- object 
	- custom data sources AWS or on prem
- ==Uses Lambda (Data Source Connector)==
- Store result in S3