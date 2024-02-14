- Classless Inter-Domain Routing - method for allocating IP addresses

Has two components:
1. Base IP - any IP contained in the range
2. Subnet Mask - How many bits can change for an IP
	1. Two Forms- 
		1. /8 <-> 255.0.0.0
		2. /32 <-> 255.255.255.255

### Subnet Mask 
1. 4 octets in an IP 
2. /32 means no octet can change - 1 IP 
3. /24 means last octet can change
4. /16 means last two octets can change
5. /8 means last three octets can change 
6. /0 all octets can change 

![[Pasted image 20240204121451.png]]
https://www.ipaddressguide.com/cidr
