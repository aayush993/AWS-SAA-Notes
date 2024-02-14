- Specify Different ways to access our S3 bucket.
- ==Simplifies security management for S3 buckets== 
- Each access point has:
	- its own DNS name (internet or VPC)
	- an access point policy ( similar to bucket policy)- manage security at scale
![[Pasted image 20240124212057.png]]

## Access Points - VPC Origin 
- we need VPC endpoint to make our access point accessible from VPC Origin.
- Endpoint Policy must allow access to the target Access point and S3 bucket.
- ![[Pasted image 20240124212236.png]]