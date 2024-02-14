Auto scaling group
- For varying loads
- Scale Out/In
- Ensure min/max instance running
- Auto register new instances to Load balancer
- Recreate unhealthy Instances
- Free service pay for Underlying EC2

#### Launch Template
- AMI + Instance Type
- EC2 User Data
- EBS Volumes
- Security Groups
- IAM Roles
- SSH Key Pair
- Network + subnet info
- Load balancer Info
Max/Min/Initial capacity
Scaling Policies

## Launch Configuration vs Launch Template
- Launch template is recommended and new features like using on-demand and spot instances together is available 
- Launch configuration cannot be modified. But template can have multiple versions 
#### Auto-Scaling
Use [[CloudWatch]] Alarms for monitoring a metric (Ex: AverageCPU of all ASG instances)
Based on that:
	Define Scale Out or In policy

#### Dynamic Scaling Policies
1. Target Tracking 
2. Simple/Step Scaling
3. Scheduled Actions
4. Predictive Scaling

#### Metric To Scale
1. CPUUtilization
2. RequestCountPerTarget
3. Average Network In or Out
4. Any custom metric: pushed using cloud watch


#### Scaling Cooldown
- After scaling activity, we are in cooldown period. 
- Default 300 seconds 
- Fine-tune the cool down period based on the requirement of applications 

## Review Notes 
- Maintenance on EC2 without detaching from ASG 
	- Move EC2 to standby
		- choose to decrease or not ASG capacity 
		- Health check - same as was before standby
	- Suspend processes on ASG 
		- ReplaceUnhealthy
- Other ASG processes
	- Launch, terminate 
	- AddToLoadBalancer, AZRebalance 
	- AlarmNotification 
	- HealthCheck, ReplaceUnhealthy 
	- InstanceRefresh, ScheduleActions
- Launch Configuration tenancy 
	- Default VPC tenancy - shared tenancy 
	- Default value for Launch configuration is null. It takes VPC tenancy value.
	- can set tenancy to default or dedicated.
- Tenancy of Instance after launch 
	- if launched with default, cant be changed to dedicated and vice versa.