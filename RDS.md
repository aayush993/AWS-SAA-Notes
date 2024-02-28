Amazon Relational Database Service. 
- Managed DB service for SQL Db's
- 6 Engines:
	- Postgres
	- MySQL
	- MariaDB
	- Oracle 
	- Microsoft SQL Server
	- [[Aurora]] 

>Provisioned RDS Instance Size and EBS Volume Type and Size. Auto scaling for storage.

>***Cannot SSH into your instances***
> For access [[RDS Custom]]
#### Advantages
As it is managed:
1. Auto provision, patching 
2. Continuous backup and PITR(Restore)
3. Monitor through dashboards
4. [[RDS Read Replicas]] for improved read performance
5. [[RDS Multi-AZ]] setup for DR.
6. ==Maintenance windows== for upgrades
7. ==Scaling capability (vertical and horizontal)==
8. Storage backed by [[EBS]] (gp2 or io1)

#### RDS Storage Auto Scaling
- Dynamic storage scaling on RDS automatically when required.
- Set Max Storage threshold (for DB)
- Scale storage if:
	- Free storage < 10% of allocated storage.
	- low storage lasts at least 5 min
	- 6 hours have passed since last modification
- For applications with un-predictable workloads

More Concepts:
[[RDS Backups & Monitoring]] 
[[RDS & Aurora Security]]
[[RDS Proxy]] 
[[RDS & Aurora MySQL Migrations]] 
[[RDS - Invoke Lambda & Event Notifications]]
## RDS Maintenance and Downtime.
- HW Maintenance
		- 1 AZ - unavailable for few minutes 
		- Multi-AZ - If maintenance for Primary AZ. It fails over to secondary in 60 sec
			- if secondary no down time. 
- OS Maintenance 
		- Only failover downtime 
		- secondary updates first 
		- failover 
		- and then primary 
-  DB Engine maintenance
		- Both primary and secondary updates at same time. 
		- Downtime is based on DB Size.

## RDS Enhanced Monitoring
- Enhanced monitoring enables monitoring of OS of your DB in real time. 
- Stored in cloudwatch for 30 days.
- We can change the retention
- RDS Enhanced monitoring 
	- Shows Primary/Secondary cluster metrics
	- Shows OS Processes
	- Shows RDS Child processes
	- Shows RDS Processes
	- Shows size, physical mem, cpu and total memory used by process.
