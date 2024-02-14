- It supports multi-node, parallel jobs which enables you to run single jobs that span multiple EC2 instances.
- Easily schedule jobs and launch EC2 instances accordingly 
--------
- Fully managed 
- batch job = has a start and end 
- Dynamically launch 
	- EC2 
	- Spot Instances 
- Provisions right amount of  compute / memory 
- submit / schedule a batch job that's it 
- Jobs are defined as Docker images and run on ECS
	- anything that can run on ECS can run on batch 
- Helpful for cost optimizations and focusing less on infra


## vs Lambda 
- Time limit. Batch has no time limit 
- Limited runtimes: no problem in batch as long packaged as Docker images 
- Limited disk space: Rely on EBS/ Instance store 
- Serverless: Not serverless