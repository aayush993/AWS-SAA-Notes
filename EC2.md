Amazon Elastic Cloud Compute

- Infra as a Service
- [[Bound to Region]]
- Capability:
	- Rent VM EC2
- Various [[EC2 Instance Types]]  for various use cases.
- [[EC2 Hibernate]] feature
- Placement of EC2 Instances can be defined by [[EC2 Placement Groups]]
- Save [[AMI]] for customizations
- High availability with [[ELB]]
- Scaling with [[ASG]]
##### Size and Config
- OS - Linux, Win, Mac
- CPU
- RAM
- Storage- 
	- Network attached - [[EBS]], [[EFS]]
	- Hardware: [[EC2 Instance Store]]
	-  Refer [[EBS vs Instance Store vs EFS]]
- Network card: speed of card, public IP
- Firewall: [[Security Groups]]
- Bootstrap script: [[EC2 User Data]]

> Private IP persists but Public IP changes on restart.
> For fixed IP use [[Elastic IP]]
### Billing
- Stopped instance: no bills
	- Instance state persisted.
- Various [[EC2 Purchasing models]]
##### Connect To EC2 vis SSH(22)
3 ways:
1. SSH
2. Putty
3. EC2 Instance connect
	1. No need for key file, temp key are uploaded onto EC2 by AWS
	
> ***Always use IAM roles for providing access to EC2 instead of Access keys.***

## Review Notes 
1. [[CloudWatch Alarms]] - Alarm action for EC2 recovery or any other action.
2. EC2 Lifecycle
	1. ![[Pasted image 20240223110739.png]]
	2. Billing 
		1. Only running instances are billed 
		2. Reserved instances in terminated state are also billed. 
		3. Stopping 
			1. for hibernate is billed 
			2. for stop is not billed.
3. Changes in EC2 on stop and restart (Only for EBS backed Instance)
	1. EBS, Private Ipv4, IPv6, EIP are all intact. 
	2. Underlying host may change.
4.  Instance store backed instances -  can only reboot or terminate 
	
5. EC2 Limits 
	1. Limited to running On-demand instances per your vCPU-based on-demand instance limit
		1. purchasing 20 RI per region
		2. and dynamic spot limit per region
		3. More limit can be asked by applying to AWS and it will be considered.