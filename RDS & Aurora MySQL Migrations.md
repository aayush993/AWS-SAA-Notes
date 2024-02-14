## MySQL 
- RDS MySQL to Aurora MySQL 
	- Option1- DB snapshots from RDS MYSql restored as Aurora MySQL DB 
	- Option 2- Create Aurora read replica from RDS and when replication lag is 0. promote it as its own cluster 
		- takes time and network cost 
- External MySQL to Aurora 
	- Option 1 
		- Use Percona XtraBackup to create file backup in S3 
		- Create Aurora DB from S3
	- Option2 
		- create an aurora MySQL DB.
		- Use mysqldump utility to migrate MySQL into Aurora 
		- slower than S3 method
- Use DMS if both DB are up and running. 
## PostgreSQL
- RDS PostgreSQL to Aurora PostgreSQL 
	- same as MySQL
- External PostgreSQL to Aurora PostgreSQL
	- create a backup put on S3
	- import it using aws_s3 aurora extension.
- Use DMS for up and running migrations

[[RDS Backups & Monitoring]] 