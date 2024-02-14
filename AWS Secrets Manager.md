- Newer Service
- ==Force rotation of secrets in X days capability== 
- Automate generation of secrets on rotation (uses lambda)
- Mostly ==meant for RDS Integration== (MySQL, PostgreSQL, Aurora)
	-  Integrations - Credentials for RDS, DocumentDB, Redshift and Other DB
	- Or Other secrets - key value pairs
- Secret encryption - KMS
- we get ==sample code to retrieve secret in your application==.

## Multi-Region Secrets
- Secrets replicated to multiple region 
- Primary is in sync with Read replicas 
- Read-replica can be promoted to independent secret 
- Use case
	- Multi-region apps 
	- DR strategies 
	- Multi-region DB

## Price
- 0.40$ per secret per month 
- 0.05$ per 10000 API calls
- 30 day free trial