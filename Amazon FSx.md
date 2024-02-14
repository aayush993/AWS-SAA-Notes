- Fully managed service 
- launch 3rd party high performance file systems on AWS.

## FSx for Windows (File Server)
- is a fully managed Windows file system share drive
- Supports ==SMB== & Win NTFS protocol
- Microsoft AD integration, ACLs, user quotas
- ==Can also be mounted on Linux EC2 instances==
- Supports Microsoft Distributed File System Namespaces (groups files across multiple FS)
- Scale up to 10s of GB/s, millions of IOPS, 100S PB of data
- Storage :
	- SSD - latency sensitive workloads
	- HDD- broad spectrum of workloads
- can be accessed from on-prem infra (VPN or Direct connect)
- configured to be ==multi-AZ==
- Data is ==backed up daily to S3==

## FSx for Lustre(Linux + Cluster)
- Lustre is type of ==parallel distributed file system for large scale computing== 
- Use: Machine Learning, ==High Performance Computing (HPC)==
- Scales up to 100s GB/s, million IOPS, sub-ms latencies
- Storage Options
	- SSD- low latency, IOPS intensive 
	- HDD: Throughput intensive workloads
- ==Seamless S3 integration==
	- read S3 as file system 
	- write back to S3
- Use with on-prem (VPN or Direct Connect)
- Review Notes:
	- Hot and cold data storage with S3

## FSx Files System Deployment Options 
1. Scratch File System: temp, highburst
	1. Temporary Storage 
	2. No replication 
	3. High burst 
	4. Short term processing 
2. Persistent File System: long term, replica DR
	1.  Long term 
	2. Same AZ replica 
	3. can replace failed files in minutes 

## FSx for Netapp ONTAP
- Managed Netapp Ontap on AWS
- ==File System compatible : NFS, SMB, iSCSI== 
- ==Broad range of OS support including EKS, ECS== and VMWare etc.
- Storage ==shrinks and grows.== automatically 
- Snapshots, replication, low-cost, compression and data de-duplication 
- ==Point in time instantaneous cloning (helpful for testing new workloads)==


## FSx for OpenZFS
- Manages OpenZFS on AWS
- ==Files system: NFS== 
- Move Workloads of OpenZFS in AWS 
- OS compatibale same as Netapp 
- Up to 1000000 iops with ==0.5 ms latency== 
- Snapshot, compression and low-cost 
- ==Point in time instantaneous cloning ( helpful for testing new workloads)==
