Load balancer uses SSL certificate for decrypting in-flight encryption of client requests.
- Load balancer uses X.509 certificate (SSL/TLS server certificate)
- Manage certificates using [[AWS Certificate Manager]]
- Upload your own certificates
- HTTPS listener:
	- Specify default certificate 
	- Add optional list for multiple domains 
	- Clients can use SNI to specify hostname they wanna reach
	- Ability to specify security policy supporting older version of SSL/TLS (legacy clients)


#### SNI 
Server Name Indication 
- SNI solves problem of loading multiple SSL certificates one web server (to serve multiple websites)
- its new: require client to specify server name and accordingly server find the correct certificate or return default one. 
- only for ALB and NLB, Cloudfront.

Can be set while setting up listener on LB.
 certificates can be from ACM, or IAM (not recommend for domain) or import