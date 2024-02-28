## Incorrect 
1. Eventbridge can invoke ECS Task directly. 
	- EC2 app cannot be invoked directly.
2. AWS KMS supports 2 types of custom key stores
	- AWS CloudHSM key store - backed by CloudHSM Cluster
	- External key store - backed by external key manager outside AWS
3. Partition key in DDB ensure 
	- that requests are spread across logically unique portions 
	- and hence maximize the throughput 
	- Recommendation for Partition key 
		- use high cardinality attributes
		- use composite attributes 
		- cache popular items 
4. Canary release deployment for testing new version of API gateway 
	- promote if testing works out.
5. [[RDS]] enhanced monitoring
6. IAM Db authentication for RDS . Uses short lived tokens.
7. Lambda is faster in terms of scaling while bursts of traffic. 
	- It scales in seconds than minutes for ECS. 
8. Using SAML based federation for AWS access
	- Users need not be created in AWS IAM. 
	- Can login with their own U/P (AD identity)
	- Uses AWS STS API to get temporary credentials. 
	- similar to Cognito Identity Providers.
9. EC2 Metrics available in [[CloudWatch Metrics]]
	- CPU metrics
	- Network metrics 
	- Disk metrics
10. AWS Artifact for compliance related information
	- Provides AWS Security and compliance reports and NDA agreements
	- All AWS accounts have access to AWS Artifact 
	- Access to non-admin IAM accounts can be given.
11. Aurora auto scaling can help in increasing Read replicas for aurora
	- has to use reader's endpoint.
12. EFS IA and EFS Archive transition 
	- can be 1 day to week and biweekly or monthly 
	- 2 month, 3 or 6 ,9 or a year 
	- No 2 yearly
13. EKS integration with Secret manager to store key value store data.
14. DataSync vs Storage Gateway 
	- DataSync is popular for existing data migration and scheduling data migrations.
	- Storage Gatway is preferred when we want to retain access to migrated data and for ongoing updates.
15. CloudWatch Alarms can target EC2, ASG Scale, SNS.
	- remember when sending monitoring via CloudWatch
17. SQS vs KDS
	- SQS is cheaper as we pay for only what we use. 
	- If real time processing is not required go for SQS.
18. Revise Route 53 policies.
19. Control access to S3 via endpoints 
	- use endpoint policy for each accessing party 
	- instead having one S3 bucket policy for all principals
20. Amazon SWF
	- Simple workflow service 
	- Allows to coordinate distribute application components
21. [[S3 Static Website Hosting]] 
	- pre-requisite for routing S3 static site to Domain name
22. Consolidating department usage of AWS resources 
	- Use tags for resources to tag them to departments 
	- enable cost allocation tags
23. SQS limits 
	- retention - 4 days default and max 14 days
	- Can have unlimited messages
	- Limit for in-flight messages 
		- standard 120000
		- FIFO 20000
24. AWS Security Token Service (STS)
	- create and provide trusted users temporary security credentials
25. EBS volumes support live config changes while in production.
	- like IOPS, type and size
26. we need dedicated connections for all accounts Transit gateway is better option.
	- To connect to transit gateway we need a direct connect gateway.
27. Only one [[EFA]] per EC2
28. [[EC2]] billing FAQs
29. [[EC2 Hibernate]] enable condition, cannot be enabled after created.
30. [[Route 53 Routing Policy]] Diff between Active-Active and Active-passive failover.
31. Cross Account S3 bucket copy permissions 
	- configure cross account permissions 
	- using bucket policy in source account and IAM policy attached to IAM user or role in account B. 
32. Changes in [[EC2]]  on restart
33. Tags can be applied using tag policies for monitoring untagged resources use AWS config
34. [[AWS Backup]] can be used to automate backups and set retention 
	- for eg for RDS we can have retention of 35 days for automated backups 
	- but with AWS backup we can set our own retention. 
39. [[Containers on AWS]] 
	- By default fargate is given 20 Gib of free ephemeral storage. 
40. [[Parameter Store vs Secrets Manager]] - cost is biggest factor.
41. Provisioned IOPS 
	- Latency sensitive workloads - low queue length 
	- Throughput sensitive - High queue length 
	- io2 block express - 1000IOPS:1GB
	- io1 50:1
42. Non SAML supported identity store we cannot use SSO
	- Federated identity with STS and custom identity broker. 
43. Storage Optimized vs Memory optimized instances 
	- Storage Optimized designed for workloads that require high, seq rw access. Good for DBs
	- Memory optimized - good for in-memory DB. Good for NoSQL. Not good for seq access
44. If data is set to be replicated for redundancy already. no worries using Instance store. 
45. Scaling Infra for EKS, Kubernetes metrics and kubernetes cluster autoscaler.
46. RDS supports auto failover only in case of Multi-AZ 
	- if we want to failover to cross region replica, manual steps are required.
47. HTTP->HTTPS
	- for existing listener set redirect rule.
48. S3 Public access 
	- give via bucket policy 
	- set public access at bucket level 
	- set at account level 
	- set while uploading the object in S3
49. To avoid duplicates
	- use SQS FIFO 
	- Use step functions
		- ensures one task is never duplicated.
50. Large amount of application log file collection and processing 
	- S3 and EMR
51. AWS Personal Health Dashboard vs Service health dashboard 
	- Service - shows public event effecting various customers in a particular region. 
	- personal - account specific.
52. Target tracking scaling policy adjusts capacity of the group based on the target value for a specific metric instead of set of scaling adjustments. 
	1. Simple scaling adjusts based on single scaling adjustment.
	2. Step scaling - increases based on set of adjustments, vary based on the size of the alarm breach.
	3. Schedule is for predictable load changes.
53. Cloudtrail logs are  by default encrypted. 
54. Running parallel simulations in cloud 
	1. Fargate we can run but the underlying infra has to be autoscaling 
	2. Batch has tools to run jobs in parallel we dont have to worry about running a job. It takes care of running it on EC2 instances.
55. EC2 taking time to boot up in ASG causing delays 
	1. use step scaling with warm up time conditions. 
56. CloudHSM 
	1. have standby in another AZ 
	2. if loose the keys, AWS does not have access to it. 
	3. So you loose it. 
57. ALB Health checks HTTP and HTTPS 
	1. NLB support TCP, HTTP and HTTPS
58. TA refresher with lambda 
	1. write lambda to refresh service limits from Trusted advisor 
	2. send the limits to cloudwatch
	3. configure alarm and send notification to SNS, SQS or Lambda
59. EKS cluster authentication for IAM entities is enabled AWS IAM authenticator for Kubernetes, running on EKS control plane.
	1. AWS authenticator config map
	2. helps in joining nodes to cluster and maintaining RBAC access for IAM users and roles
60. NFS - File gateway 
61. ISCSI - Volume/ tape gateway
62. Optional-Access logs feature for ELB
	1. you can save them in S3 bucket
63. Aurora failover 
	1. if there are read replica - failover 
	2. if aurora serverless - recreate in different AZ 
	3. if nothing, will try to recreate in same AZ. 
64. EFA supports only linux 
	1. ENA supports windows as well.
65. AWS Appsync lets you create flexible API to securely access, manipulate and combine data from one or more data sources.
	1. has a custom domain feature for HTTPS COMMS
	
66. Cannot use Network Firewall for Geo restriction 
	1. use WAF 
	2. use CloudFront 
67. For Remote virtual desktops use Amazon workspaces
68. Scaling up and down multiple times within an hour 
	1. adjust cooldown period. 
69. Karpeneter to scale number of nodes in EKS 
	1. Kubenetes metric server to EKS cluster and activate horizontal pod scaling,
## Doubts 
1. S3 Glacier Access
	- Expedited retrival
	- 1 Unit Provision capacity means 150mb/s data throughput and 3 expedited retrievals per 5 minute
	- Can purchase provision capacity units to make sure throughput is available at all times.
2. Aurora parallel query push down and distribute the computational load of a single query across thousands of CPUs in Aurora's storage layer Accelerates analytical queries while limiting the effect on transactional capability of DB.
3. No extra cost for RDS Storage Auto scaling.
4. We cannot change provisioned Aurora instance to Serverless.
	- We can make a replica as serverless and promote after replication. 
	- But this may result in downtime during failover.
	- Better to use DMS
	- 
1. We can sell Unused Reserved instances on Marketplace.
2. CreationPolicy Attribute of cloud formation
	- Associate this attribute with a resource, to make sure the resource state is not set to create complete state.
	- Waits for signal
	- cn-signal script or Signal API can be used to signal this.
3. Each subnet is associated with main route table.
	- implicitly it has local route.
4. KDS default retention 24 hours. Can be extended upto 365 days. 
5. Programmatically access your cost and usage by cost explorer API
