- ==Must enable versioning.== 
- Buckets ==can be in different AWS Accounts.== 
- Copying is ==ASYNC== 
- must give proper IAM permission to S3 

#### Use Case
- Cross Region Replication 
	- Compliance
	- Low latency access
	- replication across accounts
- Same Region Replication 
	- Log aggregation 
	- live replication between production and test accounts.

## Note
- After replication enabled, new objects are replicated. 
- To replicate existing objects 
	- ==use S3 batch replication ==option. 
	- replicate existing or failed replications 
- For DELETE Operations 
	- Can replicate delete markers from source to target ( optional setting)
	- Permanent delete ( with version) are not replicated ( to avoid malicious deletes)
- No chaining of replication 
	- A-> b-> C

[[S3 Replication Encryption Considerations]] 
