1.  [[AWS Snow Family]]  
2. [[Amazon FSx]]  Have to be revised always
3. [[Storage Gateway - (For Hybrid Cloud)]] 
4. [[AWS Transfer Family (FTP, FTPS, SFTP)]] 
5. [[AWS DataSync]] 


## AWS Storage Cloud Native Options 
1. Block - EBS - EC2 Instance Store 
2. Filesystem - EFS, FSx
3. Object - S3, Glacier

## Storage Comparison
- S3: Object Storage 
- S3 Glacier: Object Archival 
- EBS volumes: Network storage for one EC2 instance at a time 
- Instance Storage: Physical storage for your EC2 instance (high IOPS) 
- EFS: Network File System for Linux instances, POSIX filesystem 
- FSx for Windows: Network File System for Windows servers 
- FSx for Lustre: High Performance Computing Linux file system 
- FSx for NetApp ONTAP: High OS Compatibility 
- FSx for OpenZFS: Managed ZFS file system 
- Storage Gateway: S3 & FSx File Gateway, Volume Gateway (cache & stored), Tape Gateway 
- Transfer Family: FTP, FTPS, SFTP interface on top of Amazon S3 or Amazon EFS 
- DataSync: Schedule data sync from on-premises to AWS, or AWS to AWS  (s3 efs fsx)
- Snowcone / Snowball / Snowmobile: to move large amount of data to the cloud, physically 
- Database: for specific workloads, usually with indexing and querying