- AWS services are exposed Publicly 
- Using VPC endpoints (powered by AWS PrivateLink)
	- allows you to connect to AWS services using private network 
- They are 
	- redundant
	- scale horizontally 
	- ==remove need of NATGW, IGW to access web services== 
- In case of issue check:
	- DNS setting resolution for VPC 
	- Route tables

## Types 
#### Interface Endpoints 
- Provisions an ENI as an entry point 
- must attach a Sec group to it 
- Support most AWS services 
- ==$ per hour + $ per GB of data processed==

#### Gateway Endpoints (S3, DDB)
- Provisions a gateway 
- must be used as target in a route table 
- Does not use sec groups
- Supports only S3 and DynamoDB
- ==Free==

## What is preferred for S3
- Gateway mostly 
- Cost is factor 
- ==Interface Endpoint in advanced scenario== 
	- On-prem connection 
	- different VPC or different region

## Configure Endpoint 
1. On your private instance, create IAM  role to read S3. 
2. Now you can access S3 from your private Instance through internet 
3. Now if we dont have internet access. 
4. Provision a gateway endpoint the wizard updates the route table automatically
5. You have access to S3 again.