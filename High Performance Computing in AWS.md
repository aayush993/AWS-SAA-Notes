### Data Transfer
- DX
- Snow Family 
- DataSync 

### Compute & Networking 
- EC2 - on-demand and Spot, CPU Optimized and GPU Optimized
- EC2 - Cluster PG
- EC2 Enhanced Networking (SR-IOV)
	- High Bandwidth, Higher Packet per second, lower latency 
	- Option1: [[ENA]] 
	- Option2: Intel 82599 VF up to 10Gbps -LEGACY
- [[EFA]]
### Storage 
- [[EBS Types]]: Upto 256000 IOPS with io2 Block express. 
- [[EC2 Instance Store]] : scale to millions of IOPS 
- [[EFS]] : scale IOPS based on total Size, use provisioned IOPS
- [[Amazon FSx]]: for lustre, HPC optimized, millions of IOPS, S3 support

### Automation and Orchestration
- [[AWS Batch]] - to schedule parallel jobs on multiple EC2 instances
- [[AWS Parallel Cluster]] - Open source cluster management tool to deploy HPC on AWS.