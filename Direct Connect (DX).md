- Dedicated private connection from remote network to your VPC 
- must be setup between your ==DC and AWS Direct connection location== 
- Setup VGW on your VPC.
- Access ON SAME CONNECTION
	- public resources - S3 via Public VIF (No VGW)
	- Private resources - EC2 via Private VIF and VGW 
- Use case:
	- Increase bandwidth throughput 
	- More consistent network 
	- Hybrid env
- Supports IPv4 and IPv6
- Take time to establish - ==more than 1 month==

-![[Pasted image 20240205134139.png]]

## Connecting to VPC's in Different Regions
- Connect AWS Direct connection location to ==Direct connect Gateway==.
- Then ==Direct Connect gateway== to the VPC's
- ![[Pasted image 20240205134312.png]]

## Connection Types 
1. Dedicated Connection - 1Gbps, 10 Gbps and 100 Gbps capacity 
	1. Physical ethernet port dedicated to a customer.
	2. Request made to AWS first, then completed by AWS Direct Connect Partners. 
2. Hosted Connection - 50 Mbps, 500Mbps to 10Gbps
	1. Conn req vis AWS direct connect partners
	2. Capacity can be added or removed on demand.
	3. 1, 2, 5, 10 Gbps available at select AWS Direct connect partners.

## Encryption 
- Data in transit is not encrypted. 
- AWS Direct Connect + VPN for IPsec - encrypted private connect
- Good for sec but complex to put in. 
![[Pasted image 20240205134928.png]]

## Resiliency 
![[Pasted image 20240205135048.png]]