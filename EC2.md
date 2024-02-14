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