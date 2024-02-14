Encrypt objects with 4 methods:

1. Server-Side Encryption (SSE)- SSE S3, SSE-KMS, SSE-C
2. Client Side Encryption 

#### SSE S3 
1. Encryption using Keys handled, managed and owned by AWS 
2. Object is encrypted server side 
3. Encryption type: AES256
4. Must set header "x-amz-server-side-encryption":"AES256"
5. Enabled by default for new objects and buckets

#### SSE-KMS
1. Manage your keys using [[AWS KMS]] 
2. more user control + audit key usage using cloudtrail
3. server side
4. Must set header "x-amz-server-side-encryption":"aws:kms"
5. Limitations:
	1. impacted by KMS Limits 
	2. on Upload, GenerateDataKey KMS API 
	3. on download, Decrypt KMS API
	4. KMS quotas for req/s are based on region. can be increased using console. 
	5. but t==his can take you in throttling kind of scenario.==

#### SSE-C
1. Keys managed outside of AWS. 
2. S3 never stores it. 
3. HTTPS must be used. 
4. Key provided in HTTP headers for every request made. 
5. ==can only be enabled from CLI==, not from console.

#### Client Side Encryption
1. Client must encrypt/decrypt  data themselves.
2. Customer fully manages the encryption cycle.
3. ==Use client library:Amazon S3 Client Side Encryption Library.==

#### Encryption in Transit (SSL/TLS)
1. S3 exposes 
	1. HTTP
	2. HTTPS
2. HTTPS is recommended
3. HTTPS is mandatory for SSE-C
4. Force transit encryption 
	1.  apply a bucket policy denying any HTTP connection.

#### Default Encryption vs Bucket Policy
1. SSE-S3 is on by default.
2. Optionally, force encryption by denying any API calls without encryption headers. 
3. As bucket policies are evaluated before default encryption.
4. ![[Pasted image 20240124190614.png]]