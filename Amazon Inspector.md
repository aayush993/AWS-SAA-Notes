- Automated Security Assessments 
- EC2- 
	- Use SSM agent 
	- analyze unintended network access
	- OS ==vulnerabilities== 
- Container images - ECR - 
	- vulnerabilities
- Lambda functions 
	- code and package 
- Reporting to ==AWS Security Hub== 
- Send ==events to EventBridge==

## What it Evaluates 
- Only for ==EC2, ECR, Lambda==
- ==Continuous scanning of infra only when needed== 
- Checks 
	- Package vulnerabilities - database of CVE is updated
	- Network Vulnerabilities 
- risk score is associated with vulnerability for prioritization