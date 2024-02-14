- Another service on top of AWS Organizations 
- easy way to 
	- Setup 
	- Govern
	- secure and compliant multi-account  AWS environment
- Uses Org to create accounts
- Benefit
	- Automate setup of environments 
	- Automate ongoing policy management using Guardrails 
	- Detect policy violations and remediate them 
	- Monitor compliance through an interactive dashboard

## GuardRails
- Provides governance for your control tower environment 
- 2 types 
	- Preventive Guardrails - using [[AWS Organizations Service Control Policies]] - EG : RESTRICT REGIONS ACROSS all accounts
	- Detective Guardrails - using [[AWS Config]] - EG: IDENTIFY UNTAGGED RESOURCES
		- identify  -> trigger non compliant event to SNS -> notify and trigger lambda to remediate