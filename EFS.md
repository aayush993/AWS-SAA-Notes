Amazon Elastic File System
- Managed NFS used for mounting on EC2
- ==Scale automatically, pay-per-use, no cap planning==
- [[Bound to Region]] 
- Highly available, scalable and expensive(3xgp2)
- Use case: content management, web serving, data sharing, wordpress.
- Compatible with Linux AMI (not windows)
- Uses NFSc4.1 Protocol
- ==Posix Filesytem(Linux) with standard file API==
![[Pasted image 20240112152435.png]] 

#### EFS Performance
1. EFS Scale:
	1. 1000S of concurrent NFS clients, 10 GB+ throughput
	2. Grow to Petabyte scale network file system, automatically.
2. ==Performance mode==(set at creation time), Options:
	1. General purpose(default)- ***latency sensitive*** use cases (web-server, CMS, etc...)
	2. Max IO- higher latency, ***throughput****, highly parallel (big data, media processing..)
3. Throughput Mode:
	1. Bursting - 1TB = 50Mb/s + burst of up-to 100Mb/s
	2. Provisioned- set your throughput regardless of storage ex: 1GB for 1TB storage
	3. Elastic- auto scales throughput up or down based on workloads
		1. Up to 3GB/s for reads and 1Gb/s for writes 
		2. Used for Unpredictable workloads

#### EFS Storage Class:
1. Storage Tier ( Lifecycle management feature)
	1. Standard : freq access
	2. Infrequent Access (IA): cost to retrieve files, lower price to store, enable EFS-IA with lifecycle policy
2. Availability and Durability
	1. Standard- multi AZ, great for prod
	2. One Zone: for Dev, backup enabled by default, compatible with IA(EFS OneZone IA)
	3. Over 90%cost savings

## Review Notes
1. For multi region collaboration use VPC peering.