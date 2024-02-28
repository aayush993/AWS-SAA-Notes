Amazon Aurora 
- Amazon Proprietary
- Postgres and MySQL
- Cloud Optimized
	- 5x better performance over MySQL RDS
	- 3x Postgres RDS
- Storage ==auto scales in increments of 10GB== upto 128Gb
- Upto 15 replicas and faster replication process than MySQL(==sub 10ms replica lag)==
- Instantaneous failover. HA native
- 20% more cost than RDS.
- No free tier
#### High Availability and Read Scaling 
1. 6 Copies of data across 3 AZ. 
	1. 4 out 6 for writes 
	2. 3 out 6 for reads
	3. Self healing with peer to peer replication 
	4. Storage is striped across 100s of volumes.
2. One Aurora Instance takes writes (master)
3. Auto failover < 30 sec
4. Master + upto 15 read replicas serving reads
5. Read replica act as Multi-AZ HA mechanism, 
	1. Priority tier (0-15) for each replica, high priority is lowest number
6. Support for ==cross region replication==

#### Reader Load Balancing and auto scaling
Using Reader endpoint in-front of read-replicas (Auto scaling based on policies)
One writer endpoint in front of master.

#### Features:
1. Auto fail over 
2. Backup recovery 
3. Isolation, security 
4. Industry compliance 
5. Push button scaling 
6. auto patching with Zero downtime 
7. Advance monitoring Routine maintenance
8. ==Backtrack==: restore data at any point of time without using backups.

#### Aurora Custom Endpoint
1. Specify custom endpoint for subset of aurora instances.
2. Ex: to run analytical queries few instances are earmarked. 
3. Once custom endpoint is specified, reader is not used. specify multiple custom endpoints for many diff workloads.

Advanced Aurora: [[Aurora Serverless]], [[Global Aurora]] and [[Aurora Machine Learning]] 