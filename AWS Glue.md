- Fully serverless service 
- Managed Extract Transform and Load service 
- prepare and transform data for analytics 
- From Glue Service, launch an ETL job and off you go

## Convert Data in Parquet format
![[Pasted image 20240129174010.png]]

## Glue Data Catalog
- Run ==AWS Glue Data Crawlers==
	- Collects and writes ==metadata== to AWS Glue Data catalog 
	- From S3, RDS, DynamoDB or compatible JDBC DBs
	- This Data catalog is then ==used for data discovery== for many diff services
		- Like Glue, Athena, Redshift Spectrum, Amazon EMR

## Concepts 
1. Glue Job Bookmarks : prevent re-processing of old data 
2. Glue Elastic views:
	1. Combine and replicate data across data stores using SQL 
	2. No custom code, Glue monitors for changes in source data
	3. Serverless
	4. Leverages a virtual table (materialized view)
3. Glue DataBrew
	1. ==clean and normalize== data - pre-built transformations 
4. Glue Studio 
	1. GUI to run, create and monitor ETL jobs
5. Glue Streaming ETL - built on Apache spark structured streaming
	1. Compatible - Kinesis DS, Kafka, MSK