- ==Gives identity to users we do not know about (Cognito)==
	- Hundreds of users
	- Mobile users
	- authenticate with SAML
- Cognito User Pools
	- Sign in functionality for app users
	- integrate with ==API Gateway & ALB== 
- Cognito Identity Pools ( Federated Identity)
	- Provide AWS cred to users so that they can access AWS resources 
	- Integrate with Cognito User pools as an identity provider


## Cognito User Pools (CUP)
- Create ==serverless database of user== for your apps 
- Simple login - username(or email) + password 
- Password reset 
- Email & Phone verification 
- MFA
- integration for users from (sign up with feature) : facebook, Google, SAML
- Integrate with 
	- API Gatway
		- User connect with cognito login and fetch token 
		- send request plus token to gateway, gateway authenticates the token with cognito 
		- and then process request 
	- ALB 

## Cognito Identity Pools (Federated Identities)
- ==Get temp AWS Credentials for external users==
- Users: CUP, 3rd party logins, etc..
- User can access AWS services directly or through API Gateway 
- IAM policies applied to users are defined in Cognito 
- customized permissions based on user_id 
- Default IAM roles for authenticated and guest users
- User can go to CUP and get a token 
	- Exchange the token for temp AWS credentials
	- Access designated service

We can give row level security in DynamoDB for fine grain access.