- Content Delivery Network (CDN)
- [[Global Service]] 
- Improves read performance, ==content is cached at the edge.==
	- Regional edge cache also available for not so hot content.
- DDoS protection, integration with [[AWS Shield]] and [[AWS WAF]] 

## CloudFront - Origins 
- S3 bucket  
	- distribute file and cache at the edge 
	- Enhanced security with CloudFront Origin Access Control (OAC)
	- OAC is replacing OAI
	- CloudFront as a ==Ingress to upload to S3==
- Origin (HTTP)
	- ALB
	- EC2
	- S3 website 
	- Custom Origin - Any HTTP backend you want including ==on-prem servers==


## vs S3 CRR
- CloudFront
	- Global 
	- files cached for a TTL
	- ==Great for static content to be available everywhere.==
- S3 Cross Region Replication 
	- must be setup for each region required
	- files updated in real-time 
	- Read Only 
	- ==Great for dynamic content needs to be available in few regions at low latency==

## Concepts
1. [[CloudFront Origin - ALB or EC2]]
2. [[CloudFront Geo-Restriction]] 
3. [[CloudFront - Pricing]] 
4. [[CloudFront - Cache Invalidation]] 


## Review notes
-  Distribution can have multiple origins based on content. 
- Origin Failover using Origin Groups(Primary and secondary origin)
- Field level encryption to encrypt upto 10 data fields in a request. So that only the applications that needs that field can access that.

## Private Content in CloudFront
- We can either use Signed URLs
- or Signed Cookies