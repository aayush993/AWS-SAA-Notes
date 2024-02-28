
1. What happens in S3, when an object is Create or Put and immediately after accessed?
	- Ans: S3 delivers strong read-after-write consistency automatically, without changes to performance and availability at no additional cost.
	- What you write will be what you read.
	- All S3 GET, PUT, LIST operations, change object tags, ACLs, or metadata are strongly consistent.

2. To process healthcare data in High Available in-memory and HIPAA-compliant Db that supports caching SQL queries.
	- Ans: ElastiCache for Redis/Memcached
	- Its HIPAA Compliant
	- supports SQL query caching
	- And is the In-memory database.

3.  AWS Organizations, Shared-centrally managed VPCs to all department accounts using highly interconnected applications
	- **VPC Sharing** to share one or more subnets with other AWS accounts within organization.
	- This helps in maintaining trust boundaries and reduce number of VPC created.
	- VPC itself cannot be shared.
	- VPC peering is not an option as it is two VPC’s talking not a centrally managed VPC.

4. Massive Volumes of data, hot and cold data, stored and processed quickly, parallel and distributed fashion.
Ans:
	- **Lustre** is the option
	- Hot data in filesystem
	- cold data in S3 for reference, can be quickly access because of seamless S3 integration.
	- Parallel and distributed filesystem.

5. To restart EC2 instance in case of failure, automated and cost efficient way.
Ans:
	- CloudWatch Alarm setup monitoring the health status of the instance.
	- In case of failure, EC2 Reboot, stop, terminate, or recover CloudWatch Alarm action can be used.
	- Using SNS and lambda functions are wastage of resources.

6.  When to Use KDS vs SQS?
	- KDS
	    - routing related records to same processor
	    - Ordering of records
	    - Ability for multiple apps to consume same stream concurrently
	    - Ability to consume records in few hours delay
	- SQS
	    - Messaging semantics and visible timeout
	    - Individual message delay
	    - Dynamically increase concurrency/throughput at read time
	    - Scale transparently

7. Once ASG is created with a launch configuration. it cannot be modified.
	- We can create new launch configuration and update our ASG with it. DELETE THE OLD ONE

8. ECS Pricing
	- EC2 launch type - charged based on EC2 instances and EBS
	- Fargate - for vCPU and memory resources that the containerized app req

9.  Blue-green deployment
	- DNS service is a great option.
	    - it may not fit use case for fast and controlled transition of traffic.
	- With Global Accelerator
	    - We can shift traffic gradually or all at once.

10. [[AWS CodeDeploy]]

11.  Transition from standard to Fifo Queue
	- If batch
	    - Make sure 3000 msg throughput
	- If normal
	    - Make sure 300 msg throughput
	- Cannot convert existing standard queue to FIFO

12.  Amazon API Gateway offers throttling capability based on token bucket algorithm.

13. Best Practices for deploying on [[AWS Lambda]]

14. [[S3 Storage Classes]] transitions

15. Stream existing data and ongoing file updates to KDS from S3
	- leverage DMS
	- Requires least time and effort
	- it allows full migration and change data capture (CDC)
	- DMS can scale up and down depending on workload

17. KDS for decoupling and process data streams in real time.

18. [[AWS Compute Optimizer]]

19.  To copy data from one region S3 bucket to another
	- Setup replication
	- Use sync command
	    - Copies only current versions
	    - preserves metadata
	    - ACls are set to full control of your AWS account
	    - run sync command again on failure you will not duplicate anything
	- We cannot use transfer acceleration to sync buckets

20. Backend on-prem in US. low latency access in ASIA
	- Use cloudfront with custom origins

21. How to achieve peak rate in SQS FIFO messaging 
	- FIFO queue can send upto 300 msg/s without batching i.e 300 API calls  per second (per method)
	- eg: if we want to send 1000 msg/s. How many msg we need to send on each API call or operation.
	- I can send up to 10 msg per operation or API Call. Making peak rate at 3000 msg/s.
	- 1000 is well within 3000. 
	- If I send 4 msg per batch. i.e. 1200 msg/s that achieves are peak rate.

22.  Doing maintenance on EC2 Instance without detaching it from [[ASG]].
	
23.  Feature of S3 that cannot be disabled once it is enabled.
		Versioning can only be suspended.
	- Bucket can be in three states
		- unversioned
		- versioning enabled 
		- Versioning suspended

24.  EFS is regional. How to collaborate in multi region setup.
	- Use VPC peering connection to make it seem like in same network. 
	- collaborate with on-prem with Direct connection or S2S VPN
	- Note: In S3 you cannot edit the object in-place.

25.  What Instance Pricing option to Use for 24x7 app and daily 8 hourly app. 
	RI and On-Demand
	- We cannot use [[Spot Instances]] - spot block feature as it ==can only be used upto 6 hours==.
	- And it is not offered to new customers now a days. 

26.  S3 Objects retention periods.
	- Versioning must be enabled for retention period object lock.
	- Two ways to apply Retention period on a object version 
		- Through a bucket default settings 
		- explicitly: 
			- specify "Retain Until Date".
			- stored in object version's metadata. 
			- this overrides default bucket settings
	- Different versions can have different retention modes and periods.

27.  How to Disable [[AWS GuardDuty]]  and relinquish all findings as well.
		Disable/Suspend Options

28.  App of EC2 and ALB block access to a country.
	- Use [[AWS WAF]] with ALB in a Amazon VPC.
		- Geo match condition
	- No cloudfront geo restriction, that is a edge solution rather than a VPC solution.

29. S3 and S3TA Pricing
	- No charges for a failed S3TA. 
	- Only accelerated uploads are charged. 
	- [[S3 Transfer Cost]] 

30.  Company needs an SMB File share to share among different offices. 
	- Use Amazon FSx File Gateway for low latency SMB access of Fsx Windows File Server storage.
	- File gateway was initially launched and was for S3. 
	- Now we have a separate one for FSx File Gatway. 

31. To have one table globally and others regional in Aurora. minimum refactor in app
	- Two Aurora clusters can be creates 
		- One Global 
		- One Regional 
	- Minimal refactor as the API to access is same. maybe connection string changes.

32.  To Ingest data with 1GB per minute velocity. and keep it for long term. 
	- To keep we can use S3. 
	- To put it in S3 we have several options. 
	- KDF vs KDS
		- KDF is a usecase for loading data and has direct integration Lambda for transformation before loading to S3. 
		- KDS on the other hand need custom coding Lambda to load to S3. 
		- For least maintenance and cost effective go with KDF. 

33.  Cost comparison for EBS vs EFS vs S3 - [[S3 Transfer Cost]]

 34.  KMS Key delete
	- Destructive operation.
	- Hence, a waiting period 7-30 days 
	- default 30 days
35. Unpredictable access patterns and freq and infreq access 
	- S3 Intelligent-Tiering is the ideal storage class for data with unknown, changing, or unpredictable access patterns, independent of object size or retention period. You can use S3 Intelligent-Tiering as the default storage class for virtually any workload, especially data lakes, data analytics, new applications, and user-generated content.

36. Create a graph comparing cost of EC2 in past 2 months and perform in depth analysis with least overhead
	 - Use cost explorer granular filtering [[AWS Billing and Cost Management]]

37. CloudWatch dashboard sharing with least privilege
	We can share dashboards and designate specific email addresses of people who can view the dashboard.
	- share dashboard link publicly 
	- Share dashboard in your account and specify third party SSO provider for dashboard access. 

28. MS AD authentication with AWS SSO 
	- 2 way trust for all AWS services (including SSO)
	- 1 way for EC2, RDS, FSx

29. Minimum overhead and cost effective way to centralize sec group management 
	- VPC Customer managed Prefix list (AWS Managed Prefix list also available)
		- contains list of CIDRs
	- Use RAM to share prefix list across org
	- Use prefix list in Sec groups or route tables
	- AWS Managed Prefix list
		- For AWS services
		- cannot be shared, created or modified or deleted 

30. Amazon Data Lifecycle Manager for EBS snapshots and AMIs
	- to automate the creation, retention, and deletion of EBS snapshots and EBS-backed AMIs.
	
31. Burstable performance instances 
	- The T instance family provides a baseline CPU performance with the ability to burst above the baseline at any time for as long as required. 
	- The baseline CPU is defined to meet the needs of the majority of general purpose workloads.
	- The T instances offer a balance of compute, memory, and network resources, and provide you with the most cost-effective way to run a broad spectrum of general purpose applications that have a low-to-moderate CPU usage.

32. AWS Local Zones
	- Single Digit milliseconds
	- When you can not deploy in your selected region you want.
	- You can extend your VPC to Local Zones
  - AWS Wavelength zones 
	- low latency for 5G devices

33. - [[AWS Organizations Service Control Policies]] - SCP permissions
34. *STUPID* - Dedicated Hosts vs Dedicated Instances
35.  [[CloudFormation StackSets]] - for provisioning resources across accounts in various regions across accounts.
36. Difference between Cname and [[Alias Records]] 
37. Launch configuration tenancy in [[ASG]] 
38. Decoupling with [[SQS - Delay Queues]] for delaying message to the queue.
39. *STUPID*  -Real-time data with [[Kinesis Data Streams]],  SQS can work but for real-time KDS.
40.  [[S3 Performance]] - S3TA vs CloudFront
41.  *STUPID* - Too many IP's and complex configurations in multiple regions. 
	- Global accelerator is better than NLB. provides 2 IP's to whitelist and region failover.
42. *STUPID* - Difference between Vertical and Horizontal scaling 
	- Vertical - scale up down 
	- Horizontal - Scale in and out.
43. [[Spot Instances]]- Persistent spot request, request opens only after you start a stopped spot instance. In case of interrupt it automatically opens again
44. [[Security Groups]] - Valid source and destination for security groups
45. [[ECS Service Auto Scaling]] - AWS Auto scaling for availability constraint can be done on ECS service's CPU Utilization on ECS Cluster.
46. Transferring data from RDS to redshift with minimal overhead - 
	- GLUE transfers in batch and need effort in writing scripts. 
	- DMS needs to be provisioned and it manages CDC for continuous changes 
	- KDS can work but we need to provision and scale shards as per requirement. Hence DMS is best.
47.  Security Group Rules
	1. By default allows all outbound access.
	2. Stateful
	3. Only Allow rules. 
	4. No deny rules
48.  Revise Security in [[RDS]]:
	1. Data at rest can be encrypted using KMS.
	2. Data in Transit using SSL/TLS. can be Setup (diff for each DB engine)
	3. Firewall and NW Isolation: Security groups and VPC
	4. Access control: IAM or DBAuth
	5. IAM authentication uses short lived tokens.(max validity 15 mins)
49. Revise [[IAM]] concepts:
	1. IAM role is both an identity and resource.
	2. It supports resource based policy.
	3. Trust policy: which specifies what principal can assume the role.
	4. Trust policy is the only resource based policy supported by IAM service.
50.  ASG Limit setting:
	1. ASG is elastic as long as minimum and maximum capacity are different.
	2. If desired capacity is not specified, it defaults to minimum. To make an app highly available minimum we need it to be deployed across 2 AZ.
	3. If you see like full proof fail over always, then go for 3 or max AZ.
	4. If you need an Idle application 2 AZ is enough for availability as it limits the cost as well.
51. Copying [[S3]] bucket contents from one region to another 
52. Client willing to wait, need to buffer messages and retry on failure
	- Spot instance 
	- SQS
54. Glue for Batch Jobs-
	1. For ETL activity to get the data ready for analytics.
	2. Cannot run custom scripts.
55.  EC2 is better for long running batch jobs as we can increase capacity as required.
56.  EBS convert io1 to gp2, As there are occasional bursts.
	-  Gp2 can handle bursts upte 16000 IOPS has capacity to consistently serve 3000 IOPS for longer duration bursts.
	- io1 is required for consistent IOPS performance.
57. Revise compute optimizer, Trust Advisor.
	-  S3 Analytics cannot save much cost as it does not recommend for 1Z-lA or glacier.
	-  Cost explorer can be better option to identify low utilized EC2 and replace them with optimal ones.
58. [[Amazon EventBridge]] revision
	1. Eventbridge can be used to send updates from AWS Apps or Third party apps.
	2. Eventbridge has integration with Third party apps.
	3. Has filtering as well.
59.  [[S3 Object Encryption]]
60. [[S3 Static Website Hosting]]
61. [[Amazon Transcribe]] vs Amazon Alexa
	- Transcribe is an ASR service.
	- Alexa - general purpose voice interaction
	- Lex - creating custom conversational interfaces
62. [[ElastiCache]] Redis vs Memcached
63. Message sent one by one at a high rate: KDS
	- batching can solve without extra costs.
	- adding more capacity can help but that will increase cost.
64. S3 event notification supports only Standard SQS.
65. S3 Objects metadata is not encrypted.
66. For session management DynamoDB vs Redis
	- Use Elasticache redis as it is the popular choice because of its fast performance and Data structure capabilities. 
	- DynamoDB can be a choice when you need something fully managed and integrated with AWS services particularly.
67. Cross region Automated backup for [[RDS Backups & Monitoring]]
68. By default dynamodb tables encrypted with AWS owned key hence no CloudTrail
69. DTO on direct connect is lower than internet and charged per GB data sent out. 
70.  Difference between S3 Select - ScanRange parameter vs S3 Byte-Range Fetch
	- S3 Byte Range Fetch - [[S3 Performance]]
		- Uses RANGE HTTP header in GET Request
	- S3 Select Feature - ScanRange Parameter
		- Parallelize ==scanning whole object== by splitting into separate S3 select requests for series of non-overlapping byte ranges.
71. Diff SSE-S3 vs SSE-KMS - unique key for each object 
	- SSE-S3 encrypts each object with unique key 
	- and key is encrypted with a root key that is regularly rotated.
78. SSE-KMS - Encryption content 
	- Key - value pair specified for encryption
	- and decryption.
79. Prioritizing of work: have separate queue and set your EC2 to prioritize the queue.
78. [[AWS Firewall Manager]] - 
	- does not support NACLs as of now. 
	- Enforces policies on few firewalls.
79. DeleteOnTermination for EBS of a Running instance can only be changed via CLI once Instance is running.
80. ASG Rebalancing vs Scaling 
	- Rebalancing AZ load- makes sures new instances are available before terminating the old ones. Not to compromise on availability.
	- Scaling - Scaling activity to remove unhealth instance first. then another activity to replace the terminated one. 
81. **STUPID** - Job runs for 30 minutes then can't use Lambda
82. **STUPID** - S3 events can be sent to SQS and one of the four instance can poll that message. Event bridge can invoke Lambda not EC2 instances.
83. If said, no application architecture changes
	- try to scale the existing compute 
	- Horizontal will be better as we can use ELB + ASG for it. 
88. S3 to S3 Big data analysis reports 
	- Use EMR
	- Use Glue
89. To serve private content in [[CloudFront]]
90. KDS and KDA
	- KDS is not scalable on its own 
	- KDA do not store after analytics 
	- KDF and Redshift is better solution. 
91. For a HA bastion host solution 
	- We can use NLB
	- as it is a Layer 4 LB. 
	- SSH is TCP based. 
	- We do SSH connection to bastion hosts. 
92. Instance Store
	- Data persists only on Reboot
	- It can only be specified while launching EC2
	- Cannot detach and attach it. 
	- AMI does not preserves its data. 
94. EC2 uses instance profiles as a container for 1 IAM role. 
	- console: create an IAM role, instance profile is created automatically with same name 
	- CLI: both are separate actions.
95. **STUPID** For ongoing replication versus existing data migration 
	- DataSync is recommended for existing data migration 
	- File Gateway is for ongoing updates and maintaining retrieval capabilities.
96. EC2 querying cryptocurrency IP is an anomaly 
	- [[AWS GuardDuty]] can be used to protect from this unauthorized behavior
	- BY Anomaly detection
	- Especially for cryptocurrency attack GuardDuty
97. Highly available setup for a single server (Non Elastic but resilient to failure)
	- ASG with MAX, MIN, DESIRED = 1
	- Across 2 AG 
	- Elastic IP attach via EC2 user data 
	- roles for EC2 Instance to attach EIP 
	- ALB can also be used but it will be unnecessary cost.
98. [[EBS]] - RAID configurations 
99. S3 can be used for HA document store.
100. [[RDS]] - maintenance windows and Downtime

## Doubted Questions
1. EC2 instances on recovery 
	- retains public IPV4
	- losses all in-memory data.
2. [[AWS Availability Zones]] - To coordinate Availability Zones across accounts, you must use the _AZ ID_, which is a unique and consistent identifier for an Availability Zone.
3. [[Route 53]] - 
	- To resolve any DNS queries for resources in the AWS VPC from the on-premises network
		- create an Resolver inbound endpoint on Amazon Route 53 Resolver 
		- create an Resolver outbound endpoint for Route 53 to on-prem
		- Resolvers are region bound like VPCs

4. instance store volumes and EFA are not supported for automatic recovery by Amazon CloudWatch alarms.
5.  [[CloudFront]] origin failover

 6. Revise [[Amazon QuickSight]] sources, Athena cannot analyze data in real time.
    
7. [[API Gateway ]]caches from 300 seconds to 1 hour.
    
8. [[Elastic inference Accelerator ]]
9.  Link-Local addresses
	- Non routable IP addressed
	- EC2 uses addresses from this space to provide services accessible only from EC2 Instance. Services running on EC2 underlying host.
10. Retrieve user-data and meta-data from within EC2 Instance using URIs. 
	![[Pasted image 20240218213115.png]]
11. AWS tasks only  root account user can do:
	- change account name or root password or root email address
	- change AWS support plan
	- close AWS account
	- enable AWS Multi-Factor Authentication (AWS MFA) on S3 bucket delete
	- create Cloudfront key pair
	- register for GovCloud.
12. Snowmobile vs Snowball , 10PB< OR 10TB
13. [[EC2 Placement Groups]] - Partition never share racks.
14. enableDNSSupport and enableDNSHostname for VPC
15. AWS SQS Temporary Queues 
	- Creating virtual queues by using Temporary queue client.
	- Save development and deployment time, high throughput message pattern.


 