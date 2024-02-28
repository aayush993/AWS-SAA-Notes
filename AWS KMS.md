- key Management Service 
- Fully integrated with IAM 
- Audit ==KMS Key usage using CloudTrail==
- Seamlessly integrated with AWS services 
- Use KMS through API calls (SDK, CLI)
	- Use: like encrypting passwords in your code and storing them.

## KMS Key Types
- KMS Key new name for KMS Customer Master Key
- Symmetric (AES 256)
	- Single encryption key 
	- Used by services integrated with KMS 
	- ==Must call KMS API ==to use the key. 
- Asymmetric (RSA, ECC Key pairs)
	- Public (Encrypt) and Private (Decrypt)
	- ==Public available for download==, Private can't be accessed unencrypted.
	- Use: good for users encrypting outside AWS.
Different Types of KMS Keys:
1. AWS Owned Keys (free) - 
	1. eg: SS3-S3, SSE-SQS, SSE-DDB(Default)
	2. rotation handled by AWS
	3. Not stored in you AWS account and hence not tracked by CloudTrail.
2. AWS Managed Key(free) - 
	1. eg: aws/service-name
	2. rotation handled by AWS ==auto 1 year rotation.==
3. Customer Managed Key (1$/month)
	1. If imported - it should be symmetric 
		1. only manual rotation
	2. + pay for API Calls (0.03$/1000 calls)
	3. Controlled Auto Rotation: ==must be enabled- every 1 year==

### Keys are Bound to a Region
- When we copy encrypted snapshot across region.
- Same KMS Key cannot live in two regions 
- Hence, AWS creates a new KMS Key in the new region for the copy snapshot.

## KMS Key Policies
- Like S3 Bucket Policies 
- ==Diff: cannot manage access without them== 
- Default KMS Key Policy 
	- Created if no policy provided
	- Complete access to root user = AWS account
- Custom KMS Key Policy 
	- Define user or roles accessing KMS Key 
	- Who can administer the key 
	- Useful for ==cross account access==

## Copy Snapshot across account
1. Eg: we have a customer managed Key in our account 
2. We want to copy snapshot across account and use this key in target account to decrypt 
3. We assign Custom KMS Key policy to a role in target account who can access to our key from source account.
![[Pasted image 20240201180541.png]]


## Review Notes
- Key deletion is destructive 
	- waiting period 7-30 days after deletion (default 30)