
Q1:  Backend on-prem in US. low latency access in ASIA
- Use cloudfront with custom origins

Q5: How to achieve peak rate in SQS FIFO messaging 
- FIFO queue can send upto 300 msg/s without batching i.e 300 API calls  per second (per method)
- eg: if we want to send 1000 msg/s. How many msg we need to send on each API call or operation.
- I can send up to 10 msg per operation or API Call. Making peak rate at 3000 msg/s.
- 1000 is well within 3000. 
- If I send 4 msg per batch. i.e. 1200 msg/s that achieves are peak rate.

Q6: Doing maintenance on EC2 Instance without detaching it from ASG.
Ans: 
- Move EC2 Instance in standby 
	- You can choose either to decrease ASG capacity 
	- Or not to, in that case new EC2 replaces standby instance
	- We are billed for Standby EC2 Instances as well.
	- Health check: reported as it was before it was in standby. 
	- Once you are done, you can set it Inservice
- Suspending processes on ASG 
	- There are many processes which can be suspended for ASG, while performing maintenance tasks. 
	- Processes:
		- Launch, Terminate 
		- AddToLoadBalancer, AZRebalance
		- AlarmNotification
		- HealthCheck, ReplaceUnhealthy 
		- InstanceRefresh, ScheduleActions
	- We can use ReplaceUnhealthy Option to suspend and match our use case. 

Q14: Feature of S3 that cannot be disabled once it is enabled.
Ans: Versioning can only be suspended.
	- Bucket can be in three states
		- unversioned
		- versioning enabled 
		- Versioning suspended

Q16: EFS is regional. How to collaborate in multi region setup.
ANS
	- Use VPC peering connection to make it seem like in same network. 
	- collaborate with on-prem with Direct connection or S2S VPN
	- Note: In S3 you cannot edit the object in-place.

Q23: What Instance Pricing option to Use for 24x7 app and daily 8 hourly app. 
Ans: RI and On-Demand
- We cannot use spot blocks as it ==can only be used upto 6 hours==.
- And it is not offered to new customers now a days. 

Q28: S3 Objects retention periods.
Ans
- Two ways to apply Retention period on a object version 
	- Through a bucket default settings 
	- explicitly: 
		- specify "Retain Until Date".
		- stored in object version's metadata. 
		- this overrides default bucket settings
- Different versions can have different retention modes and periods.

Q33: How to Disable Guard Duty and relinquish all findings as well.
[[AWS GuardDuty]] 
Ans: Disable/Suspend Options
- Just choose disable option under services tab
- suspend option will stop it from looking at your logs but will not delete existing findings.

Q35: App of EC2 and ALB block access to a country.
- Use WAF with ALB in a Amazon VPC.
	- Geo match condition
- No cloudfront geo restriction, that is a edge solution rather than a VPC solution.

Q 39: S3 and S3TA Pricing
Ans:
	- No charges for a failed S3TA. 
	- Only accelerated uploads are charged. 
	- [[S3 Transfer Cost]] 

Q43: Company needs an SMB File sare to share among different offices. 
Ans: 
- Use Amazon FSx File Gateway for low latency SMB access of Fsx Windows File Server storage.
- File gateway was initially launched and was for S3. 
- Now we have a separate one for FSx File Gatway. 

Q55: To have one table globally and others regional in Aurora. minimum refactor in app
Ans: Two Aurora clusters can be creates 
	- One Global 
	- One Regional 
	- Minimal refactor as the API to access is same. maybe connection string changes.

Q56: To Ingest data with 1GB per minute velocity. and keep it for long term. 
- To keep we can use S3. 
- To put it in S3 we have several options. 
- KDF vs KDS
	- KDF is a usecase for loading data and has direct integration Lambda for transformation before loading to S3. 
	- KDS on the other hand need custom coding Lambda to load to S3. 
	- For least maintenance and cost effective go with KDF. 

Q58: Cost comparison for EBS vs EFS vs S3
- EFS - 0.30$ per GB , 0.016$ per GB
- S3: 0.023$ per GB
- EBS - charged per provisioned GB  for gp2 i.e 0.10$
- So correct sequence is per GB - S3 < EBS < EFS
- But if provision more that is in most cases. Eg: EBS 100GB = 10$
- then S3 < EFS < EBS
- For EBS 
	-

Q59: KMS Key delete
- Destructive operation.
- Hence, a waiting period 7-30 days
- default 30 days