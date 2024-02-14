- We have various sec tools 
	- NACLs 
	- Sec groups 
	- WAF
	- [[AWS Shield]] 
	- [[AWS Firewall Manager]] 
- To protect our VPC we also have Network Firewall
	- From layer 3 to layer 7 attacks 
- Any direction traffic can be inspected
	![[Pasted image 20240205150933.png]]

- Internally uses [[Gateway Load Balancer]] with AWS managed security appliances. 
- Rules can be centrally managed by [[AWS Firewall Manager]] to apply to VPCs across accounts 

## Fine grained controls 
- Supports 1000S Of rules
	- IP & port - filtering 
	- Protocol - block SMB for outbound 
	- Stateful domain list - only allow outbound to a certain domain 
	- General pattern matching using regex
- Traffic filtering: allow, drop or alert for traffic 
- Active flow inspection - intrusion prevention 
- Send logs of matching rules to S3, CloudWatch Logs or KDF