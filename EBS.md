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


#### EBS Snapshots
- Point in time backup 
- detach not required for this
- Can be ==copied across AZs==
- Can be used to recover volume in another AZ
- ==Can be locked== to prevent accidental deletes
- Features
	- Move Snapshot. Standard > archive tier, 24-72 hr retrieval
	- Recycle bin, retention after deletion
	- ==Fast Snapshot Restore(FSR):== forced full initialization snapshot for no latency on the first use($$$) 