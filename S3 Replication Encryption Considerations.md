- [[S3 Replication]] 
- By Default: Unencrypted and Encrypted Objects (SSE-S3) are replicated.
- SSE-C - can be replicated 
- SSE-KMS - need to enable 
	- Specify a Target encryption key for target bucket 
	- Give KMS Key Policy for Target Key 
	- IAM Role- for source KMS Key - to decrypt
	- IAM Role - for target KMS Key - to Encrypt 
	- KMS Throttling - ask for service quota increase

## Can set Multi Region Keys but they are still treated as independent keys by S3. So has to be decrypt and encrypt operation