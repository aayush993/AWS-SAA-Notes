## Encryption At Rest 
1. [[AWS KMS]]: Manage Encryption Keys, Key Types, Key Policies, Keys are bound to region.
2. [[AWS KMS Multi-Region Keys]]: Primary+Replicas, For usecase like Global DynamoDB
3. [[S3 Replication Encryption Considerations]] - Diff Keys - SS-S3, SSE-C, SSE-KMS
4. [[Share Encrypted AMI across Accounts via KMS]] - Process of cross Account AMI share

## Secret Management
1. [[SSM Parameter Store]] - ==Serverless==, To store parameter securely.
2. [[AWS Secrets Manager]] - New Secret storing with forced rotation capability. mostly for RDS credentials
3. [[Parameter Store vs Secrets Manager]]

## In-Flight Encryption 
1. [[AWS Certificate Manager]] 

## Firewalls
1. [[AWS WAF]] : Firewall for layer 7 applications
2. [[AWS Shield]] : DDoS Protect
3. [[AWS Firewall Manager]] : Manage firewall across account, automate protection of new resources
### WAF vs Shield vs Firewall manager
- WAF - granular resource protection 
- org wide across account protection - WAF + Firewall manager
- Shield advanced - prone to DDoS - good choice
### DDoS protection best practices - Revise Architecture Video
1. First Best practice: if we are the edge better DDoS protection. CloudFront, Global Accelerator, Route 53
2. Infra level best practice
	1. LB and Edge - protect application layer from attacks
	2. ASG - helps in scaling 
	3. ELB - helps in distributing
3. Application layer defense: Layer 7 Defense
	1. Cache 
	2. WAF + Cloud Front and ALB - rules to filter requests 
	3. Shield Advanced
4. Attack surface reduction 
	1. obfuscating AWS resources 
	2. Sec groups and Network ACLs
	3. Protecting API endpoints

## Security Tools
1. [[AWS GuardDuty]] : Intelligent threat discovery using ML and data already present in Logs.
2. [[Amazon Inspector]] - assessing vulnerabilities - CVE
3. [[Amazon Macie]] - Identify alert on sensitive data


[[AWS Security Hub]] 