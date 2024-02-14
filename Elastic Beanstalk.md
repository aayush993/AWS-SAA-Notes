Developer centric view of deploying an app on AWS. 
Uses all components: EC2, ASG, ELB, RDS,...
It's Managed service:
	1. Auto handles 
		1. capacity provisioning
		2. LB
		3. scaling
		4. app health monitoring
		5. instance config
	2. Just app code is developer's problem
==User have full control over the config.==
==Beanstalk is free== but underlying infra is chargeable. 
Supports many programming platforms. If not supported you can write custom platform.


#### Components
1. Applications: collection of Elastic Beanstalk components (environments, versions, config)
2. Application Version: iteration of app code. 
3. Environment
	1. Collection of AWS resources running on a version of app code. 
	2. Tiers: web server environment Tier & worker env tier (SQS)
	3. Can Create multiple environments
![[Pasted image 20240116132633.png]]


#### Deployment Modes
1. Single instance: great for dev. Elastic IP
2. HA with LB : great for prod. ALB