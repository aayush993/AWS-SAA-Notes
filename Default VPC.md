- All new accounts have a default VPC 
- New EC2 launched in that if no subnet specified. 
- Has 
	- Internet connectivity 
	- EC2 instances have Public IPv4 addresses
- Public and private IPv4 DNS names

#### Default Subnet
- By default we have three subnets
	- Each in one AZ for High availability

#### Default Subnet settings
- For these subnets we have default route table. 
- default Network ACLs , allowing all in and out traffic.
- default auto assign public address option is enabled for all of them
- ==VPC Flow logs are not enabled by default== for this.

#### Default Route Table 
- it tells how our network is routed through our VPC. 
- Destination our CIDR - target is local 
- Destination internet - target should be Internet gateway attached to our VPC.
- It is implicitly assigned to subnet by default. 