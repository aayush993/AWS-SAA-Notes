- SSO for all your 
	- AWS accounts in AWS organizations
	- Business cloud applications (eg: salesforce, MS 365)
	- SAML2.0- enabled apps
	- EC2 Windows Instances 
- Identity Providers:
	- ==Built in identity store== in Identity center
	- 3rd party: AD, OneLogin, Okta

For eg: You have multiple AWS accounts
1. you can login with your SSO
2. You will go to you IAM Identity Center page. 
3.  Click on any of your accounts and you will go to AWS console logged in with that account. 
![[Pasted image 20240131141449.png]]

## Permission Sets
1. You create a user in identity center (which is ==in your Management account==). eg: developer
2. you ==create a permission set== with full access to specific OU and then this permission set is ==assigned to your user==. 

## Fine grain permissions and Assignments 
1. Multi account permissions 
	1. manage access across AWS accounts in AWS org
	2. Permission sets for users and groups
	3. ![[Pasted image 20240131142246.png]]
2. Application Assignments 
	1. SSO access to many SAML 2.O apps (eg: sales force)
	2. Provide required url, certififcates etc.
3. ==Attribute based Access Control (ABAC)==
	1. acess control based on user attributes stored in Identity center
	2. Usecase: define permission once and then just change attributes for users. 
	3. eg: junior senior.