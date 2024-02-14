- DB based on ==PostgreSQL==
- Not for OLTP but for ==OLAP== 
- 10x better performance than other Data warehouses, ==scales to PBs of Data== 
- Columnar storage of data instead of row based
- Parallel query engine 
- Pay as you go based on instances provisioned 
- ==SQL interface for performing queries== 
- BI tool integration : Quicksight, tableau

## vs Athena
- Athena for ADHOC query on S3 data 
- Loading data not required 
- Redshift load required 
	- faster queries 
	- faster joins / aggregations 
	- More intense queries ==thanks to indexes==

## Redshift cluster 
- ==Leader node ==for query planning and result aggregation 
- ==Compute node== for performing queries, send result to leader 
- ==Provision node in advance== 
- Use Reserved Instances for cost savings 

## Concepts 
1. [[Redshift - Snapshot and DR]]
2. [[Redshift - Data Ingestion]]
3. [[Redshift - Spectrum]]