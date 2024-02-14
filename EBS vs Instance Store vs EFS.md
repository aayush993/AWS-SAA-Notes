[[EBS]] 
- One instance (expect multi attach io1/io2)
- Bound to AZ
- gp2: IOPS increaser if disk space increases
- gp3  & io1: can increase independently 
- Migrate AZ: using snapshots
- EBS Backups uses IO, avoid in traffic 
[[EFS]]
- Mounting 100s of instances across AZ 
- To share website files
- Only for linux 
- Higher price 
- leverage IA for cost save
[[EC2 Instance Store]] 
- Very High IOPS
- Used for temporary content