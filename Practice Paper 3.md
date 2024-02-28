- [[AWS Organizations Service Control Policies]] - SCP permissions
- *STUPID* - Dedicated Hosts vs Dedicated Instances
- [[CloudFormation StackSets]] - for provisioning resources across accounts in various regions.
- Difference between Cname and [[Alias Records]] 
- Launch configuration tenancy in [[ASG]] 
- Decoupling with [[SQS - Delay Queues]] for delaying message to the queue.
- *STUPID*  -Real-time data with [[Kinesis Data Streams]],  SQS can work but for real-time KDS.
- [[S3 Performance]] - S3TA vs CloudFront
- *STUPID* - Too many IP's and complex configurations in multiple regions. 
	- Global accelerator is better than NLB.
- *STUPID* - Difference between Vertical and Horizontal scaling 
	- Vertical - scale up down 
	- Horizontal - Scale in and out.
- [[Spot Instances]]- Persistent spot request, request opens only after you start a stopped spot instance. In case of interrupt it automatically opens again
- [[Security Groups]] - Valid source and destination for security groups
- [[ECS Service Auto Scaling]] - AWS Auto scaling for availability constraint can be done on ECS service's CPU Utilization on ECS Cluster.
- Transferring data from RDS to redshift with minimal overhead - 
	- GLUE transfers in batch and need effort in writing scripts. 
	- DMS needs to be provisioned and it manages CDC for continuous changes 
	- KDS can work but we need to provision and scale shards as per requirement. Hence DMS is best.

## Doubted Questions
- EC2 instances on recovery 
	- retains public IPV4
	- losses all in-memory data.
- [[AWS Availability Zones]] - To coordinate Availability Zones across accounts, you must use the _AZ ID_, which is a unique and consistent identifier for an Availability Zone.
- [[Route 53]] - 
	- To resolve any DNS queries for resources in the AWS VPC from the on-premises network
		- create an inbound endpoint on Amazon Route 53 Resolver 
		- create an outbound endpoint for Route 53 to on-prem

### Correct
- instance store volumes and EFA are not supported for automatic recovery by Amazon CloudWatch alarms.
- thumb rule -
	- Think resource performance monitoring, events, and alerts; think Amazon CloudWatch.
	- Think account-specific activity and audit; think AWS CloudTrail.
	- Think resource-specific history, audit, and compliance; think AWS Config.