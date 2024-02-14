- Hub and spoke connection : For having transitive peering between 
	- Thousands of VPC
	- On-prem (Works with DX or VPN Connections)
- ==Regional==, can work cross region 
- Share cross- account, using Resource Access Manager (RAM)
- ==Peer transit gateways== across regions
- Control routing - route tables limiting which VPC can talk to which
- Support ==IP Multicast (only service to support it)==
![[Pasted image 20240205135738.png]]
## Transit Gateway : S2S VPN ECMP enhancement
- ECMP - Equal Cost Multi Path 
- Strategy to forward packet over multiple best path 
	![[Pasted image 20240205140110.png]]
- Throughput with ECMP 
	- Transit gateway uses 2 tunnels which is better than VPN to VGW which uses 1 tunnel. 
	- we can increase these tunnels in Transit gateway by having multiple Connections. 
	- VPN TO VGW - 1 connection with 1.25Gbps  and only 2 tunnels 
	- VPN TO Transit gateway = 1 connection with 2 tunnels with 2.5Gbps ECMP
		- We can 2x or 3x this with multiple connections.
		- Will draw more cost per GB of DATA processed.
## Share Direct Connect between Multiple Accounts using Transit Gateway
- Connect on-prem with Direct connect endpoint 
- Attach endpoint to direct connect gateway. 
- Connect Direct connect gateway to Transit gateway 
- and connect VPC in different accounts to connect to Transit gateway.
- We can use AWS Resource Access manager to share transit gateway with other accounts.

![[Pasted image 20240205140632.png]]