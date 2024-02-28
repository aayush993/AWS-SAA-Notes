
- Easily Provision managed and deploy ==TLS Certificates==.
- Support
	- Public TLS Certs
	- Private
- Free for Public certificates.
- Automatic ==renewals==. 
- Integrations with (load TLS Certs on)
	- ELB
	- CloudFront Distributions 
	- APIs on Gateway
- ==Cannot use for EC2==

## ACM Requesting Public Certificates
1. List domain names to be included in certificate 
	1. FQDN : corp.example.com 
	2. Wildcard domain: *.example.com
2. Select validation method
	1. DNS Validation : preferred for automation, leverage cname for DNS config
	2. Email validation : send email to contact to verify 
3. Will take a few hours to get verified. 
4. Public certificate will be enrolled for auto renewal. 
	1. ==ACM auto renews - 60 days prior to expiry for ACM generated certs==


## ACM Importing Public Cert
1. generate cert outside and import to ACM
2. ==No Auto renewal: manual renew==
3. Expiry ==Notification== 
	1. Eventbridge: ACM sends by ==default 45 days before==, number can be configured
	2. AWS Config: use ==acm-certificate-expiration-check==, get non compliant event in eventbridge

![[Pasted image 20240203222940.png]]

## ACM Integrate with API Gateway

for Edge-Optimized - certificate lives in us-east1
for regional- in same region as API Gateway
![[Pasted image 20240203223224.png]]