	TWO: SQL and Flink 

## For SQL
- Real time Analytics with SQL statements 
- Fully managed, no servers to provision
- Source : KDS and KDF 
- Output: KDS or KDF
- Enrich streaming data from S3 
- Auto scaling 
- Pay for actual consumption rate 
- Use: Time-series analytics 
	- Real-time analytics 
	- Real-time metrics

![[Pasted image 20240126232309.png]]

## For Apache Flink 
- Renamed to Amazon Managed Service for Apache Flink. 
- Use Flink(Java, Scala or SQL) to process and analyze streaming data. 
- ==Sources are only: KDS and [[Amazon MSK]] (Not KDF)==, 
- Run any Apache Flink application on managed cluster on AWS 
	- provision compute, parallel computation, auto scaling 
	- application backups (checkpoints and snapshots)
	- Use any Flink programming feature 

Also using other sources.