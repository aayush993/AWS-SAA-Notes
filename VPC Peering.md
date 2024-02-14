- Privately connect two VPCs using AWS network 
- Use case: To make two VPC behave they are in same network 
- Must not have overlapping CIDRs
- VPC Peering is not transitive.
- To establish 
	- ==establish peering== 
	- ==Update route tables in each subnets== to ensure connection.

## Note 
1. Can Peer VPCs in different AWS ==regions/Accounts== 
2. ==refer sec group== from Peered VPC (across account or region)
![[Pasted image 20240204232848.png]]


Peering request has to be accepted. 
Modify our private VPC's subnet route table to route all the traffic for VPC Peer CIDR to peering connection.
Modify route table for Peering connection VPC, for other VPC CIDR to peering connection