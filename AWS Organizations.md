- [[Global Service]] 
- Allows to manage multiple AWS accounts 
- ==Main account = management account== 
- ==Other= member accounts== 
	- Can be part of one organization 
- Billing benefits 
	- Consolidated billing across all accounts 
	- Benefits of aggregated usage of services across accounts 
	- ==Shared reserved Instances and savings plans discounts==
- ==API available to== create an account within an organization.

## How it Works? - Organizational Units
- ==Root OU having management account inside.== 
- Inside Root OU we can have two OU: DEV and PROD 
- DEV - Member Accounts 
- PROD - Member Accounts 
- PROD - HR OU and Finance OU
Organize however you want. 

![[Pasted image 20240131123902.png]]


## Organizations Advantages
- Multi Account vs 1- Account MultiVPC 
- Tagging standards for billing purposes
- Enable CloudTrail on all accounts, send logs to central S3 bucket 
- Send CloudWatch logs to central logging Account
- Establish Cross Account Roles for Admin Purposes. 
- Security with [[AWS Organizations Service Control Policies]]
## Notes 
- Either we can create new member accounts or invite an existing account. 
- invitation has to be accepted. 
- We can enable multiple types of policies in Organizations 
	- Backup Policies - organization wide backup plans 
	- Tag policies - standardize tag usage 
	- SCP- this is very powerful, can limit member root accounts

## Review Notes
1. VPC Sharing to share one or more subnets with other AWS accounts within organization. 
	1. Use case: when a shared centrally managed VPC is required. 
2. [[CloudFormation StackSets]] 