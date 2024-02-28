- SYNC replication
- ==One DNS name== - auto failover standby
- Increase availability
- Failover for: Network, instance or storage failure
- No intervention in apps. 
- Not for scaling.
- ***Read Replicas can be set as Multi AZ for DR***


#### Single AZ to Multi AZ
- Zero downtime 
- modify db to multiAZ
- This happens BTS:
	- Snapshot taken
	- new DB is restored from snapshot in new AZ
	- SYNC is establishes in DB's