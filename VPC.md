- Virtual Private Cloud 
- can have multiple VPCs in a AWS region 
- Max CIDR per VPC is ==5==
- Each CIDR
	- Min - /28 (16 IP )
	- Max - /16 (65536 IP)
- Because VPC is private only private ranges are used. Refer [[Public vs Private IP]]
- ==Choose any range, just make sure IP do not overlap with your other networks.== 

Two ways to create:
1. Launch VPC wizard 
2. Or build each component manually

Note: 
- When we create a VPC, default route table, ACLs are created with it.
- No subnets are created by default in new VPC.

## Building a VPC
1. Let's create a [[Subnet]].
2. Let's give Internet Access to our Public hosts in Private VPC using both
	1.  [[Internet Gateway - IGW]] 
	2. Route Tables with adding route for anywhere target be IGW
3. Internet access for Private hosts 
	1. Inbound access: [[Bastion Hosts]]: SSH bastion host and then SSH to your private hosts.
	2. Outbound access: [[NAT]] 