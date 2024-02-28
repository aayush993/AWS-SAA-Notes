Elastic Block Store
- Network drive, hence latency
- One Instance at a time 
- Provisioned Capacity: size and IOPS, can be increased over time.
-  30GB free tier
- [[EBS Types]]  
- [[EBS Multi-Attach]]
- [[EBS Encryption]] 
- [[Bound to AZ]] 
	- To move take a snapshot.

#### Delete on termination attribute
Enable/disable to retain root volume after EC2
>By default EBS created with EC2 will be deleted on termination.
**`DeleteOnTermination`**
Can be set to False at the time of creating an instance. 
Once Instance is running, you can update it via CLI.


#### EBS Snapshots
- Point in time backup 
- detach not required for this
- Can be ==copied across AZs==
- Can be used to recover volume in another AZ
- ==Can be locked== to prevent accidental deletes
- Features
	- Move Snapshot.==Standard > archive tier== , 24-72 hr retrieval
	- Recycle bin, retention after deletion
	- ==Fast Snapshot Restore(FSR):== forced full initialization snapshot for no latency on the first use($$$)


## RAID Config
 EBS, you can use any of the standard RAID configurations that you can use with a traditional bare metal server.
 1. RAID 0 - for high performance 
 2. RAID 1 - for fault tolerance and data protection
 3. RAID 5 - Balnce both 
 4. RAID 6 - HA and Performance

RAID 1 is not recommended
	Requires more EC2 EBS bandwidth as data is written to multiple volumes simultaneously. 
RAID 5 and 6 not recommended
	parity write consume some of the IOPS.
	Less IOPS available to the disk 
	Cost is also more. 
