- Network Address Translation 
- Allows EC2 in private subnet contact the internet 

- Must be in public subnet 
- Must disable EC2 setting: ==source/destination check== 
- Must have ==elastic IP==
- ==Route tables== must be configured to route traffic ==from private subnets to NAT instance==

## Network Packet re-write
- It changes network packet - changes the source on the packet to it's own IP and when 
- It receives reply - it replaces destination as the private EC2 IP

## Notes
- Pre-configured Amazon AMI is available 
	- EOS on Dec 31 2020
	- Search "nat" in AMI's find latest

- ==Need to handle Infra config yourself==
	- Not HA/ Resilient out of box 
		- Need to create ASG in multi-az
		- resilient by user data script
	- Internet traffic b/width depends on EC2 type 
	- Must manage Sec Group & rules:
		- Inbound 
			- Allow HTTP/HTTPS traffic from Private Subnets 
			- Allow SSH from home network 
		- Outbound 
			- Allow HTTP/HTTPS traffic to internet

## How to provision 
1. Create a NAT instance 
2. In Private EC2 sec group, route all traffic with destination anywhere to Elastic IP of NAT
3. in NAT instance Sec group, 
	1. Allow HTTP, HTTPS from private subnet CIDR
	2. Allow SSH from home network 
	3. Allow ICMP from private subnet CIDR