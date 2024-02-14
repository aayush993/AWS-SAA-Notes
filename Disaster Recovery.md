## DR
- DR is about preparing for recovery in event of disaster
- Kinds 
	- On-prem -> On-prem - traditional, costly 
	- on-prem -> Cloud - Hybrid
	- Cloud Region A -> Cloud Region B
- DR Objective : Optimizing for
	- RPO - Recovery Point Objective - Data loss
	- RTO - Recovery Time Objective - Downtime
- Smaller RPO, RTO higher the cost

## DR strategies
1. Backup and Restore (High RPO and High RTO)
	1. Very easy. Deploy a Storage Gateway for S3 backups or 
	2. Use snowball edge 
	3. Take EBS snapshots 
	4. In face of Disaster, restore from backups. 
	5. ==Cheap== : We don't manage infra for DR, just recreate when needed
2. Pilot Light 
	1. Small version of app with critical core systems are always running in cloud. 
	2. Faster than backup and restore as critical system already running ![[Pasted image 20240206132517.png]]
3. Warm Standby
	1. Full system up and running in cloud ==at minimum scale==. 
	2. Upon disaster failover to cloud and scale. 
	3. Costly but Low RPO and RTO![[Pasted image 20240206132709.png]]
4. Multi Site / Hot Site Approach 
	1. ==Active Active setup==
	2. very low RTO (min or seconds)
	3. very expensive 
	4. Full prod scale running in AWS and Onprem ![[Pasted image 20240206132849.png]]

## All AWS Multi Region
![[Pasted image 20240206133010.png]]

## Tips
1. Backup 
	1. EBS Snapshots, RDS automated backups/Snapshots etc...
	2. Regular push to S3, lifecycle policy, cross region replication 
	3. From on-prem : snowball or storage gateway 
2. HA
	1. Use Route 53 for DNS migrate over from region to region 
	2. RDS Multi AZ, ElastiCache MultiAZ, EFS, S3
	3. S2S VPN as conn backup for DX
3. Replication 
	1. RDS Replication (Cross Region), AWS [[Aurora]]  + Global DB 
	2. DB replication from On-prem to RDS
	3. Storage Gateway 
4. Automation 
	1. CloudFormation/ Elastic Beanstalk to automate new env deployment 
	2. Recover/ REBOOT ec2 With cloudwatch alarms if fail
	3. AWS lambda for automations 
5. Chaos testing