- Launching docker containers on AWS = Launching ECS tasks on ECS Clusters
- Launch Types:
	- EC2 Launch Type
		- Provision and maintain infra(EC2)
		- Each EC2 must ==run ECS Agent ==to be part of ECS Cluster 
		- AWS takes care of starting and stopping containers.
	- Fargate Launch Type
		- No provisioning, no maintaining EC2 instances 
		- ==Serverless==
		- create task definitions 
		- AWS runs Tasks for you ==based on CPU and RAM== 
		- To ==scale just increase number of tasks.==

## IAM Roles for ECS
- EC2 Instance Profile (EC2 Launch Type only)
	- Used by ECS Agent 
	- Make API calls to ECS 
	- Send logs to CloudWatch 
	- Get images from ECR
	- Refer sensitive data from Secrets manager or SSM Parameter Store
- ECS Task Role 
	- each task can have specific one 
	- defined in task definition 


## Load Balancer Integrations 
1. [[ALB]] : supported and works for most use case
2. [[NLB]]: Only recommended for High throughput /high performance use cases
	1. or to pair with AWS Private Link
3. [[CLB]]: Supported not recommended (No fargate)


## Data Volumes (EFS)
- Mount EFS file system ==on ECS Tasks== 
	- ==Works for EC2 and Fargate== 
- Task running in any AZ will share same data 
- Fargate + EFS = ==Serverless==
- Use case: persistent multi AZ shared storage for containers 
- ==S3 cannot be mounted as a file system.==

You can run a standalone task, or you can run a task as part of a service. You can use an Amazon ECS _service_ to run and maintain your desired number of tasks simultaneously in an Amazon ECS cluster.