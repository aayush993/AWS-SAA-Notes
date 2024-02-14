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

More Concepts: [[RDS Backups & Monitoring]] , [[RDS & Aurora Security]], [[RDS Proxy]] 