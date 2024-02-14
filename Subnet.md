- AWS reserves 5 Ip address (first 4 & Last 1) in each subnet
- For 10.0.0.0/24 - 256-5 ip 
- .0 for Network Address
- .1 by AWS for VPC router 
- .2 by AWS for mapping to Amazon provided DNS 
- .3 by AWS for future 
- .255 is network broadcast address. 

### Network broadcast is not supported in a VPC hence address is reseved

Exam tip - if we need 29 IPs we cannot use /27 = 32 Ip address - 5 = 27 < 29

## Auto Assign IP settings 
- We have option to enable auto assign 
	- IPV4 
	- IPV6
- This setting is by default enabled in Default VPC - Default subnet. Hence we get public IPs for our EC2.  
## Subnet Creation tips 
1. Use smaller size CIDR for public subnets. 
2. Use Bigger subnet size for Private subnets. 
3. If you are creating two subnets in VPC, create in different AZ and give successive CIDRs
