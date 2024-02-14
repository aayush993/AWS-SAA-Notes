
- ==Bridge between on-prem and cloud dat==a (to push Hybrid cloud)
- Use case: DR, Backup, tiered storage or on-prem cache
- gateway has to be installed on your on-prem datacenter

4 Types of Storage Gateways.

## 1. Amazon S3 File Gateway

![[Pasted image 20240126011401.png]]
Most recently used data is cached in the file gateway.
SMB Protocol has integration with AD for user authentication.

## 2. Amazon FSx File Gateway
![[Pasted image 20240126011600.png]]
FSx already have support for SMB or NFS. 
We can use gateway and use ==Local cache of gatway.==
Useful for group file shares and home directories.
Windows native compatibility ( SMB, NTFS, AD)

## 3. Volume Gateway
- Block storage using ISCSI
- Backed by EBS snapshots  which can help restore on-prem volumes
- *Cached Volumes* - low latency most recent data 
- *Stored volumes* - entire dataset on-prem, scheduled backups to S3
![[Pasted image 20240126011947.png]]

## 4. Tape Gateway
-  Use tape gateway to backup your physical tapes in cloud. 
- Virtual Tape Library backed by S3 and Glacier.
- using iSCSI interface
- works with leading backup software vendors
![[Pasted image 20240126012159.png]]


## Storage Gateway Hardware Appliance
If you don't have on-prem virtualization.
You can order this and use it for your gateway,