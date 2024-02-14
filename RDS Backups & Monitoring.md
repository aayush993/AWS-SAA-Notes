RDS Backups
-------
1. Automated backups: Expires, can be disabled
	1. Daily full backup (in backup window)
	2. Transaction logs are backed up by RDS every 5 minutes. 
	3. PITR up to 5 minutes ago 
	4. 1-35 days retention
	5. set to 0 to disable
2. Manual DB Snapshot: No expiry
	1. Retention as long as you want.
	2. Manually triggered

> For Stopped RDS, charges are applicable.  Take a snapshot and restore later. delete your DB.


#### Aurora Backup
1. Auto backup:
	1. 1-35 day retention 
	2. No disable 
	3. PITR
2. Manual same as RDS


#### Restore Options
1. Restore RDS/ Aurora backup to create a new DB.
2. Restore MySQL RDS from S3
	1. Create a backup of your on-prem DB
	2. store in S3
	3. Restore backup file into a new RDS instance.
3. Restore MySQL Aurora cluster from S3
	1. same process but use percona XtraBackup for creating backup

#### Aurora DB Cloning
1.  New Aurora DB cluster from existing 
2. Faster than snapshot and restore. 
3. Copy-on-write protocol
	1. Initially both DB use same data volume
	2. Once updates are made to the clone. additional storage is allocated.
4. Fast & cost-effective.
5. Useful to create a staging db from a production db without impacting the production db. 