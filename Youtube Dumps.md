
Q: Minimum overhead and cost effective way to centralize sec group management 
- VPC Customer managed Prefix list (AWS Managed Prefix list also available)
	- contains list of CIDRs
- Use RAM to share prefix list across org
- Use prefix list in Sec groups or route tables
- AWS Managed Prefix list
	- For AWS services
	- cannot be shared, created or modified or deleted 

Q: Least  Operational overhead
- Try to use feature from the same service. 

Q: Amazon Data Lifecycle Manager
- to automate the creation, retention, and deletion of EBS snapshots and EBS-backed AMIs.
Q: Burstable performance instances 
- The T instance family provides a baseline CPU performance with the ability to burst above the baseline at any time for as long as required. 
- The baseline CPU is defined to meet the needs of the majority of general purpose workloads.
- The T instances offer a balance of compute, memory, and network resources, and provide you with the most cost-effective way to run a broad spectrum of general purpose applications that have a low-to-moderate CPU usage.

Q: AWS Local Zones
A: 
- Single Digit milliseconds
- When you can not deploy in your selected region you want.
- You can extend your VPC to Local Zones
Q: AWS Wavelength zones 
A:  low latency for 5G devices