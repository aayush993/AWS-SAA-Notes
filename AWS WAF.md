- Web Application Firewall 
- works on ==Layer 7== not on Layer 4
- Deploy on 
	- ==ALB only==
	- API Gateway 
	- CloudFront (not on Global Accelerator)
	- AppSync GraphQL API 
	- Cognito User Pool

-  Define Web ACL (Web Access Control List) Rules:
		- IP Set: Upto 10,000 IP addresses - to block or allow
		- Protect from SQL Injection - Cross Site Scripting : HTTP- Headers, Body, URI strings
		- Size constraints, geo-restriction 
		- Rate based rules - DDoS protection 
		- We have many AWS managed rules to choose from.
		- We can set rule priority as well
- Web ACL - regional except CloudFront
- Rule Group: reusable set of rule can be added to Web ACLs


![[Pasted image 20240203224358.png]]


## Review Notes 
- WAF with ALB to block access to country for VPC solution 
	- geo restriction