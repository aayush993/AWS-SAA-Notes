
AWS IAM is Identity and Access Management Service
[[Global Service]]

##### IAM Has:
Authentication:
	 [[IAM User & Groups]]
	[[IAM Password Policy]]
	[[MFA]]
Authorization
	[[IAM Permissions]]
	[[IAM Policies]]
	[[IAM Roles]]
Audit
	Security Tools
Access
	[[User Access]]

##### Security Tools available:
1. ==IAM Credential Report==: gives view of account's users credential status
	1. Enforce password best practices
2. ==IAM Access Advisor==: Service permission granted to user. 
	1. History of access for that user.
	2. Helps to revise access policy

##### Best Practices:
- don't use root user.
- 1 user - 1 AWS user
- Assign permission -> group <- user
- strong password policy 
- use MFA 
- use roles for AWS service permission 
- Use Access keys for CLI/ SDK 
- Audit permission using Tools
- Never share user and access keys.


More on IAM in [[IAM Advanced]] 