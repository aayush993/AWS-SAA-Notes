1. Aurora Cross Region Read Replicas:
	1. For DR
	2. Simple to setup
2. Aurora Global DB(recommended)
	1.  1primary region (read/write)
	2. Up to== 5 secondary (read only) regions.==
	>3. Replication== lag up to 1 second==
	4. Up-to 16 Read replicas per secondary region
	5. Helps to decrease latency
	6. Promote another region in DR. RTO < 1 minute


## DB failover 
- Managed PLANNED Failover - RPO - 0
- Unplanned failover - RPO in seconds and RTO < 1 minute