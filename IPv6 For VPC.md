- IPv6 successor to IPv4 
- All are public 
- Format: x.x.x.x.x.x.x.x ( hexadecimals)

- ==IPv4 cannot be disabled for your VPC and subnets==
- Can enable IPv6 which is public for Dual stack mode
- EC2 - will at least get 
	- Private IPv4 
	- Public Ipv6
	- Can communicate to internet via internet gateway using IPv4 or IPv6

## IPv6 troubleshooting 
- ==IPv4 cannot be disabled on your VPC== 
- If unable to launch EC2 might be IPv4 space ran out 
	- IPv6 cannot run out as it is very large
- Add a CIDR to your subnet 

