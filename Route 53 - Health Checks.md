Health checks can be done ==for public resources.== 
- facilitates automatic DNS failover
- ==Integrated with CloudWatch Alarms.==

1. Monitor an Endpoint
	1. About 15 health check will check the endpoint.
		1. Healthy/Unhealthy failure threshold: 3(default)
		2. Interval -  30 sec (can set to 10 sec - higher cost)
		3. Supported - HTTP, HTTPS and TCP
		4. if >18% report endpoint is healthy. Route 53 considers it healthy.
		5. Ability to choose which locations to use for health checkers. 
	2. Pass when response is 2xx or 3xx.
	3. Can be set to pass/fail based on first 5120 bytes of response. 
	4. configure firewall to allow Route 53 Health checks,
2. Calculated Health Checks:
	1. Combine multiple health checks into a single.
	2. Use OR, AND or NOT 
	3. Can monitor up to 258 Child Health Checks. 
	4. Specify pass threshold for children to pass the parent 
	5. Usage: perform maintenance to your website without causing all health checks to fail.
3. Checking Private resources:
	1. Route 53 is outside VPC. 
	2. In private Hosted zones or private VPC. 
	3. We can create a Cloudwatch metric and associate cloudwatch alarm, then create a health check for the alarm itself. 