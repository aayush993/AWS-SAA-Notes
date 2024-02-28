- To invoke Lambda functions 
	- We can directly invoke, client should have IAM permission 
	- Or use ALB to expose HTTP endpoint
	- API Gateway: expose public rest API for client to access. Many features

## Features
1. Lambda + API Gateway = Full Serverless
2. Support for
	1. HTTP API 
	2. Rest API 
	3. WebSocket API
3. Handle API versioning 
4. Handle multiple environments 
5. Handle Security 
6. Create API Keys, ==request throttling== 
7. Swagger/Open API import to quickly define API 
8. Transform and validate requests and responses 
9. Generate SDK and API specifications 
10. ==Cache== API responses 
	1. caches from 300 seconds to 1 hour.

## Integrations 
1. Lambda function 
	1. To expose Rest API
2. HTTP
	1. Expose HTTP endpoints in the backend 
	2. For - on prem, ALB 
	3. To leverage API gateway features
3. Any AWS service 
	1. Deploy publicly with API gateway features

Example 
![[Pasted image 20240128235436.png]]

## Endpoint Types 
1. Edge optimized (Default) - global clients 
	1. Req routed through CloudFront Edge locations 
	2. API still lives in one region 
2. Regional - regional clients
	1. Manually combine with CloudFront - gives more control over caching and distribution
3. Private - clients within your VPC 
	1. can be accessed using VPC endpoint (ENI)
	2. Use resource policy to define access

## Security 
- User Auth
	- IAM Roles - internal applications
	- Cognito - for external users
	- Custom authorizer - your own logic
- ==Custom Domain Name HTTPS security== through integration with ACM 
	- Certificate in us-east1 for edge-optimized 
	- for regional in same region 
	- Must setup Cname or A-alias record in Route 53

## Default Timeout is 29 seconds regardless of underlying Lambda timeout