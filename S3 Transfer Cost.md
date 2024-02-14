- Ingress = free
- S3 to internet = 0.09$
- S3 transfer acceleration 
	- Faster transfer times (50 to 500%)
	- Addn cost on top of data transfer charge - 0.04 to 0.08 per Gb 
- S3 TO CLOUDFRONT - FREE
- Cloudfront to internet - 0.085$ per GB 
	- 7xcheaper 
	- caching capcbility 
- S3 Cross Region- 0.02$ per GB

[[S3]] Pricing 
		- Storage - per GB charge
		- Data transfer charge- 
			- No charge for in transfer from internet 
			- No charge for out to CloudFront 
			- No charge within same region. 
			- No charge out for first 100GB

## Cost Difference
EBS vs EFS vs S3
EFS - 0.30$ per GB , 0.016$ per GB
- S3: 0.023$ per GB
- EBS - charged per provisioned GB  for gp2 i.e 0.10$
- So correct sequence is per GB - S3 < EBS < EFS
- But if provision more that is in most cases. Eg: EBS 100GB = 10$
- then S3 < EFS < EBS