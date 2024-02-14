
Services:
		1. [[CloudWatch Metrics]] : Variables to monitor
		2. [[CloudWatch Logs]] : Logs from different sources
		3. [[CloudWatch log agent]] : collects logs from EC2 and send to CloudWatch Logs
		4. [[CloudWatch Alarms]]: Used to trigger notification  or action for any metric 
		5. [[Amazon EventBridge]] : Get events from AWS service, 3rd party or custom apps
		6. [[CloudWatch Insights tools]] : Insight tools to monitor, Container, lambda, contributor and Apps
		7. [[AWS CloudTrail]] : governance and audit of your AWS account
		8. [[AWS Config]] : record configuration and check compliance for our resources. 


## Diff between CloudWatch, CloudTrail and Config

- CloudWatch 
	- Performance monitoring (metrics)
	- Events and alerting 
	- Log aggregation and analysis
- CloudTrail
	- Record API calls within account 
	- define trails for resources
	- global service 
- Config 
	- record config changes 
	- evaluate compliance rules on resources 
	- get timeline for changes

For eg: each of them for ELB.


## Review Notes
- CloudWatch dashboards
	- We can share CloudWatch dashboards and designate specific email addresses of people who can view the dashboard.
	- share dashboard link publicly 
	- Share dashboard in your account and specify thrid party SSO provider for dashboard access. 