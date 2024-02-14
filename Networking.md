1. [[CIDR]]  & [[Public vs Private IP]] 
2. [[Default VPC]]
3. Let's create a [[VPC]] 
4. [[Security Groups  vs NACLs]] - like a Firewall over Subnets
5. [[VPC Peering]] - to behave two VPC as they are in same network
6. [[VPC Endpoints (AWS PrivateLink)]] - Privately access AWS services
7. [[VPC Flow Logs]]  - To troubleshoot networking issues. Sent to S3, CloudWatch Logs
8. [[VPC - Traffic Mirroring]] - to inspect the traffic on your ENI in non-intrusive manner
9. [[IPv6 For VPC]] - Public Ip addresses. can be enabled for VPC. 
10. [[Egress Only - Internet Gateway]]  - Kind of NAT gateway for IPv6 out to internet

## Connecting On-Prem and AWS
1. Over Internet -
	1. [[AWS Site to Site VPN]] - secure over internet. Needs VGW and CGW.
	2. [[AWS VPN CloudHub]] - ==Low cost Hub and spoke model== for Different locations over internet.
2. Dedicated Private Connection 
	1. [[Direct Connect (DX)]] - Private Unencrypted connection, can be used with VPN for IPSec
3. We can configure Direct Connect primary and if it fails. 
	1. We can either have DX connection secondary which will be expensive
	2. ==Or S2S connection - cheap== 
4. [[Transit Gateway]] - ==Hub and spoke model to connect VPNs==, Direct connect or S2S VPN.

## Networking Cost in AWS per GB
- All incoming traffic is free
- EC2-EC2  in same AZ - private IP - free
- EC2-EC2 different AZ - Private IP - 0.01$ per GB 
- EC2-EC2 different AZ - public IP - 0.02 per GB 
- EC2-EC2 different Region - 0.02$

- Use as much as possible private IP 
	- Cheaper 
	- High speed
- Use same AZ for max savings at cost of HA 
	- For cluster use same AZ. 
	- For RDS if you need a read replica for analytics use same AZ. 

[[Minimize Egress Network Cost]]
[[S3 Transfer Cost]]
[[Price NAT Gateway vs Gateway VPC Endpoint]] 


## Protecting Your VPC
1. [[AWS Network Firewall]]
