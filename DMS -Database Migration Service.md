- Quickly and securely migrate DB to AWS
- Supports complex db configs like secondary indexes, foreign keys and stored procedures.
- Resilient and self healing 
- ==Source== DB remains ==available== during ==migration== 
- Supports 
	- Homogeneous : same DB engine
	- Heterogeneous : diff DB engine 
- Continuous Data replication using ==CDC== 
- Must ==create an EC2 instance== to perform replication tasks.

## Source and Targets 
![[Pasted image 20240206162921.png]]

## Schema Conversion Tool (SCT)
- Convert your DB schema from engine to another
- Example : OLTP - SQL server to Aurora 
- Example: OLAP - Teradata to Redshift 
- Need to run SCT + DMS 
- You do not need SCT if you are migrating same engine 

## Setting up Continuous replication 
![[Pasted image 20240206163311.png]]

## DMS - Multi AZ  
- Sync standby replica in different AZ 
- Advantage 
	- Provide data redundancy 
	- Eliminates I/O freezes
	- Minimize latency spikes

## Provisioning DMS Instance 
1. provision a replication instances
2. create a DB migration task, choose your replication instances. 

## Review Notes 
- Use case: Stream existing data and ongoing changes from S3 to KDS