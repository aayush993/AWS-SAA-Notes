- Amazon Elastic Kubernetes Service 
- Way to launch managed Kubernetes Clusters on AWS
- Kubernetes is open-source system for auto deployment, scaling and management of containerized applications.
- Alternative to ECS
- Supports EC2 if you want to deploy worker nodes or Fargate for serverless
- Use:  Migrating to AWS for applications already using Kubernetes
- Kubernetes is cloud agnostic

## Terminologies 
- EKS Node - ECS Service 
- EKS Pod - ECS Task 
- EKS Worker Nodes - ECS EC2 Instances (Part of EKS Cluster)

- we can launch EKS Nodes with auto scaling across AZ's in private subnet. 
- We can expose them using a private LB or
- we can expose them using Public ELB

## EKS - Nodes Types
 1. Managed Node Groups 
	 1. ==Create and manage Nodes (EC2 Instances) for you== 
	 2. Nodes are part of ==ASG managed by EKS== 
	 3. Support On-Demand and Spot
1. Self-Managed Nodes
	1. Nodes created by you and register them to cluster  and managed by an ASG  
	2. You can use AMI- Amazon EKS Optimized AMI 
	3. On-Demand and Spot 
2. Fargate
	1. No maintenance required, no nodes to manage


## Data Volumes 
- Need to specify StorageClass manifest on your EKS Cluster 
- Leverages Container Storage Interface (CSI) compliant driver 
Supports
1. EBS 
2. EFS (only one supporting Fargate)
3. FSx for Lustre 
4. FSx for Netapp Ontap

## Creating EKS 
- We need to manually create a EKS role for our cluster to access other services.
- While creating Worker Node as well create a role for it. 