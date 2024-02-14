- Connects On-Prem with AWS using a encrypted connection over the internet 
- It needs two things 
	- Virtual Private Gateway (VGW)
		-  VPN concentrator on AWS side of VPN connection
		- VGW is created and attached to the VPC 
		- Possibility to customize ASN (Autonomous System Number)
	- Customer Gateway(CGW)
		- Software application or physical device on customer side of VPN connection

## Setting Up Customer Gateway 
- Customer Gateway Device (on-prem)
	- Public IP - If you have that for your CGW use the same. 
	- Private IP - In that case use NAT device enabled for NAT-T (NAT traversal). Use public IP of NAT-T 
- ==Imp Step:== Enable route propagation for VGW in route tables that is associated with subnets. 
- For ping - add ICMP on inbound of your sec groups. 
- ![[Pasted image 20240205132027.png]]

## Setting UP 
1. Create customer gateway and name it use the IP to reach it on-prem.
2. Create a VGW, 
3. Then connect theses two with S2S i.e Virtual private gateway. 