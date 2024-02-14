## Docker 
- SW dev platform to deploy apps 
- Apps packaged in containers that can be run on any OS.
- Apps run same anywhere, regardless:
	- Any machine 
	- Any Compatibility 
	- Predictable behavior 
	- Less work 
	- easy maintenance
	- any language or OS
- Use: microservices, lift and shift apps from on prem to AWS cloud
- You can run multiple containers of these apps on any server.
- Docker images are stored in Docker repositories 
	- Docker Hub : Private repo 
	- Amazon ECR(Elastic Container Registry): Private Repo and ==Public Gallery==
- How to use?: 
	- create dockerfile 
	- Push image and pull 
	- Run the image as a container


Container management on AWS:
1. [[Amazon ECS]] : Elastic Container Service. Amazon's own container platform 
	1. [[ECS Service Auto Scaling]]  
	2. [[ECS Solution Architectures]]
2. [[Amazon EKS]] : Amazon managed Kubernetes (Open source)
3. Fargate: Amazon's own serverless container platform. ECS and EKS 
4. [[Amazon ECR]]: Store container images

