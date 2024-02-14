1. Encrypted AMI in Account A with KMS Key.
2. First share the AMI by modify =="Launch permission"== specifying Target AWS account 
3. share KMS Key to Target Account /IAM Role ==KMS Key Policy==
4. I==AM Role/ User== in Target account must have access to 
	1. DescribeKey API 
	2. ReEncrypted API 
	3. CreateGrant API 
	4. Decrypt API 
5. You can launch EC2 now. You can now encrypt the volumes with new key.