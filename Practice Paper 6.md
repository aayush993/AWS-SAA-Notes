## Incorrect
- Difference between S3 Select - ScanRange parameter vs S3 Byte-Range Fetch
	- S3 Byte Range Fetch - [[S3 Performance]]
		- Uses RANGE HTTP header in GET Request
	- S3 Select Feature - ScanRange Parameter
		- Parallelize ==scanning whole object== by splitting into separate S3 select requests for series of non-overlapping byte ranges.
- Diff SSE-S3 vs SSE-KMS - unique key for each object 
	- SSE-S3 encrypts each object with unique key 
	- and key is encrypted with a root key that is regularly rotated.
- SSE-KMS - Encryption content 
	- Key - value pair specified for encryption and decryption.
- Prioritizing of work: have separate queue and set your EC2 to prioritize the queue.
- [[AWS Firewall Manager]] - 
	- does not support NACLs as of now. 
	- Enforces policies on few firewalls.
- DeleteOnTermination for EBS of a Running instance can only be changed via CLI
- ASG Rebalancing vs Scaling 
	- Rebalancing AZ load- makes sures new instances are available before terminating the old ones. Not to compromise on availability.
	- Scaling - Scaling activity to remove unhealth instance first. then another activity to replace the terminated one. 
- **STUPID** - Job runs for 30 minutes then can't use Lambda
- **STUPID** - S3 events can be sent to SQS and one of the four instance can poll that message. Event bridge can invoke Lambda not EC2 instances.
- If said no application architecture changes
	- try to scale the existing compute 
	- Horizontal will be better as we can use ELB + ASG for it. 
- S3 to S3 Big data analysis reports 
	- Use EMR
	- Use Glue
- To serve private content in [[CloudFront]]
	- We can either use Signed URLs
	- or Signed Cookies
- KDS and KDA
	- KDS is not scalable on its own 
	- KDA do not store after analytics 
	- KDF and Redshift is better solution. 
- For a HA bastion host solution 
	- We can use NLB
	- as it is a Layer 4 LB. 
	- SSH is TCP based. 
	- We do SSH connection to bastion hosts. 
- Instance Store
	- Data persists only on restart and Reboot
	- It can only be specified while launching EC2 
	- Cannot detach and attach it. 
	- AMI does not preserves its data. 
- Proprietary encryption algorithm 
	- calls for client side encryption of S3
- EC2 uses instance profiles as a container for 1 IAM role. 
	- console: create an IAM role, instance profile is created auto matically with same name 
	- CLI: both are separate actions.
- **STUPID** For ongoing replication versus existing data migration 
	- DataSync is recommended for existing data migration 
	- File Gateway is for ongoing updates
- EC2 querying cryptocurrency IP is an anomaly 
	- GuardDuty can be used to protect from this unauthorized behavior
	- BY Anomaly detection
	- Especially for cryptocurrency attack GuardDuty
- Highly available setup for a single server
	- ASG with MAX, MIN, DESIRED = 1
	- Across 2 AG 
	- Elastic IP attach via EC2 user data 
	- roles for EC2 Instance to attach EIP 
	- ALB can also be used but it will be unnecessary cost.
- [[EBS]] - RAID configurations 
- S3 can be used for HA document store.
- [[RDS]] - maintenance windows and Downtime
	

## Doubts
- Snowmobile vs Snowball , 10PB< OR 10TB
- [[EC2 Placement Groups]] - Partition never share racks.
- enableDNSSupport and enableDNSHostname for VPC
- AWS SQS Temporary Queues 
	- Creating virtual queues by using Temporary queue client.
	- Save development and deployment time, high throughput message pattern.