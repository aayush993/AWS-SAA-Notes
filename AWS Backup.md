- Fully managed service 
- Centrally managed and automate backup across AWS services 
- No need to create custom scripts or manual processes
- Supported services
	- ECS/EBS
	- S3
	- RDS / Aurora/ DynamoDB
	- Document  DB, Neptune 
	- EFS / FSx (Lustre and Win File server)
	- Storage Gateway
	- many more
- Support ==cross region,  cross account backups.== 


## Features 
- Supports PITR for supported service 
- On-demand and scheduled backups 
- ==Tag-based backup policies==
- Create backup policies : ==Backup Plans== 
	- Backup freq 
	- Backup Window
	- ==Transition to cold storage== ( Never, day, week, month, year)
	- Retention period (always, day, week, month, year)

Create a backup plan, assign eligible services and automatically backups are created into S3.

## AWS Backup Vault Lock
- Enforce WORM on backups stored in Backup Vault 
- Has a Vault Lock policy 
- Addntl layer to protect backups 
	- malicious deletes 
	- Updates that shorten or alter retention period
- even root user cannot delete
