## CloudWatch Container Insights 
- collect, aggregate, summarize ==metrics and logs== from containers 
- For
	- ECS service 
	- EKS Services 
	- Kubernetes on EC2 
	- Fargate( EKS and ECS)
- In EKS and Kubernetes: Uses a containerized version of CloudWatch Agent
- Create a dashboard out of it.

## Lambda Insights 
- Monitoring and troubleshooting solution for serverless app running on Lambda 
- Collect, aggregate and summarize 
	- ==system level metrics== including CPU, time, memory, disk and network 
	- ==diagnostic information== like cold starts and lambda worker shutdowns
- It is ==provided as Lambda Layer==
- ==detailed monitoring for lambda== 
- creates a dashboard called lambda insight 

## Contributor Insights
- analyze  log data and create time series that display contributor data 
	- See metrics for ==top -N contributors==
	- total number of unique contributors and their usage 
- Leverage cloudwatch logs
- Use: fine top talkers and who or what impacts system 
- ==Works with any AWS generated Logs== (VPC., DNS etc)
- Eg: find heaviest network Users or bad URLs
- Rules 
	- Build your own or use sample rules by AWS 
	- built in rules you can use to analyze metrics from AWS services 


## Application Insights 
- Automated ==dashboards showing potential problems with monitored apps ==to isolate ongoing problems.
- app on EC2 using various AWS services can be monitored
- Powered by ==SageMaker== 
- Enhance visibility in app health
- ==reduce troubleshoot time== 
- Finding and alert are sent to EventBridge and SSM OpsCenter

