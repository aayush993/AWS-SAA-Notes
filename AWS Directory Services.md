- What is Microsoft AD
	- On Windows Server 
	- DB of Objects - user, file shares, Security groups 
	- Centralized Domain Controller 
	- Objects = trees
	- Group = forest

### 3 AWS Directory Services 
#### AWS managed Microsoft AD
- Own AD In AWS + trust on prem AD 
- Supports MFA

#### AD Connector
- proxy auth req to on-prem AD
- Directory Gateway

#### Simple AD
- AD compatible managed directory in AWS.
- No joining with on-prem


### Integrate IAM Identity Center - AD setup
- Connect to an AWS Managed Microsoft AD
	- Integration is out of box. 
	- This in case you want to manage AD on AWS + on-preM
- Develop two way trust relationship for self managed AD
	- Connect to Managed AD and establish it's trust with on-prem 
	- connect to AD connector to proxy to on-prem