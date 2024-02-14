Elastic Network Interface
- Logical component in [[VPC]] representing virtual network card.
- [[Bound to AZ]] 
- create on the fly and attach to EC2 instances for failover
- Attributes:
	- Primary, optional one or more secondary private IPv4
	- One Elastic Public IP per private IPv4
	- One public IP
	- One or more Sec groups
	- A mac address

Use case: 
- We have a ENI already with public private IP with EC2
- We can have a secondary ENI with private IP. 
- Which can be used for failover. detach and attach

[[References]]
