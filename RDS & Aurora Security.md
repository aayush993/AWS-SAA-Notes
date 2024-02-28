1. At- rest encryption 
	1. DB master & replica encrypted using AWS KMS- defined at launch time. 
	2. not encrypted master means - replicas also not encrypted
	3. to encrypt, go through snapshot & restore as encrypted. 
2. In-flight: ==TLS ready== by default. AWS TLS root certificate client side. 
3. IAM authentication: use IAM roles to connect to your DB (instead of password)
4. SECURITY Group: control NW access
5. No SSH: except RDS custom 
6. Audit logs can be enabled and sent to CloudWatch logs for longer retention.