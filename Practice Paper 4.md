## Incorrect
- Security Group Rules
	1. By default allows all outbound access.
	2. Stateful
	3. Only Allow rules. No deny.
-  Revise Security in [[RDS]]:
	1. Data at rest can be encrypted using KMS.
	2. Data in Transit using SSL/TLS Setup (diff for each DB engine)
	3. Firewall and NW Isolation: Secgroups and VPC
	4. Access control: IAM or DBAuth
- Revise [[IAM]] concepts:
	1. IAM role is both an identity and resource.
	2. It supports resource based policy.
	3. Trust policy: which specifies what principal can assume the role.
	4. Trust policy is the only resource based policy supported by IAM service.
-  ASG Limit setting:
	1. ASG is elastic as long as minimum and maximum capacity are different.
	2. If desired capacity is not specified, it defaults to minimum. To make an app highly available minimum we need it to be deployed across 2 AZ.
	3. If you see like full proof fail over always, then go for 3 or max AZ.
	4. If you need an Idle application 2 AZ is enough for availability as it limits the cost as well.
- Copying S3 bucket contents from one region to another 
	- a. We can use Sync command for one time copy. 
	- b. We can use batch replication and delete the replication config after we are done. 
	- C. We cannot use S3TA for copy
	- We cannot use AWS Console for 1 PB data not feasible.
- Client willing to wait, need to buffer messages and retry on failure
	- Spot instance 
	- SQS
- Authentication in RDS-
	1. For increased security Access control in RDS
	2. Enable IAM authentication using IAM Role attaching to accessing application.
	3. It uses short lived tokens (max 15 minutes valid).
	4. The data in transit is SSL secure.
- Glue for Batch Jobs-
	1. For ETL activity to get the data ready for analytics.
	2. Cannot run custom scripts.
-  EC2 is better for long running batch jobs as we can increase capacity as required.
- Revise EBS concepts:
	- EBS convert io1 to gp2, As there are occasional bursts.
	-  Gp2 can handle bursts upte 16000 IOPS has capacity to consistently serve 3000 IOPS for longer duration bursts.
- Revise compute optimizer, Trust Advisor.
	-  S3 Analytics cannot save much cost as it does not recommend for 1Z-lA or glacier.
	-  Cost explorer can be better option to identify low utilized EC2 and replace them with optimal ones.
- Eventebridge revision
	1. Eventebridge can be used to send updates from AWS Apps to Third party apps.
	2. Eventbridge has integration with Third party apps.
	3. Has filtering as well.



## Doubts
- Cloud Front-
	a. Distribution can have multiple origins based on content. 
	b. Origin Failover using Origin Groups.
	c. Field level encryption to encrypt upto 10 data fields in a request. So that only the applications that needs that field can access that.

 - Revise [[Amazon QuickSight]] sources, Athena cannot analyze data in real time.
- Host based routing in ELB?
    
- API Gateway caches from 300 seconds to 1 hour.
    
- Revise Storage Family. Who supports clustering?
    
- [[Elastic inference Accelerator ]]
Revise Route 53 Routing
Revise S3 and transitions.
