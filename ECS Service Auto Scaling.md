- Automatically scale desired number of ECS Tasks.
- Amazon ECS Auto Scaling uses ==AWS Application Auto Scaling== 
	- ECS Service Average CPU utilization 
	- ECS Service Average Memory Utilization 
	- ALB Request Count per target
- Strategy:
	- Target Tracking 
	- Step Scaling 
	- Scheduled Scaling
- ECS Service Auto Scaling (Task Level) not equal to EC2 Instance level Scaling 
- Fargate is much easier to sertup (because you dont have to worry about underlying infra scaling)

## EC2 Launch Type - Auto scaling 
- We can accommodate Task level Auto scaling in two ways
	- ==Auto Scaling Group== Scaling 
		- Scale your EC2 based on CPU Utilization
	- ECS ==Cluster Capacity Provider== 
		- Used to automatically provision EC2 Instances to accommodate your ECS Tasks
		- Capacity Provider paired with ASG

![[Pasted image 20240127220242.png]]