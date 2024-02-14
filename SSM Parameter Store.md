- Secure storage for configuration and secrets 
- ==Encryption Optional ==using KMS 
- Serverless, Scalable, easy SDKs
- ==Version tracking ==of secrets 
- Security IAM 
- Notification : EventBridge 
- Integration - CloudFormation

## SSM Parameter Store Hierarchy 
- ==Use hierarchy to control access to our parameters==![[Pasted image 20240201190520.png]]
- /aws/reference/secretsmanager/secret_ID_in_Secret_manager 
	- to refer secret manager parameters.
- /aws/service/ami-amazon-linux-latest/amzn2-ami-hvm-x86_64-gp2 (public)

## Standard vs Advanced Parameter Tiers
- Number of params - 10K(ST) - 100k(Adv)
- Max Size - ==4KB (St)- 8kb(Adv)==
- Param policy - No(ST)- Yes(adv)
- Cost - Free - Adv: 0.05$ per advanced param per month

## Parameter Policy - Advanced Tier
- Assign TTL for a param - expiration date 
- to enforce update or delete sensitive data such as passwords
- Assign multiple policies 
![[Pasted image 20240201191058.png]]

## Notes- 
- It's within System Manager service. 
- We can use CLI to get params 
	- aws ssm get-parameters
	- It returns string or securestring. 
	- We need to decrypt secure string. 
	- If I have access to KMS. we can just give ==--with-decryption ==and get plain string directly
	- aws ssm get-parameters-by-path <path> --recursive
- For lambda we can use boto3 to access SSM API.
	- Give access to Lambda for SSM. 