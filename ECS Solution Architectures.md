1. ECS Tasks Invoked by Event Bridge 
	1. Client uploads to S3 
	2. S3 Sends Event to EventBridege 
	3. EventBridge has a rule to run ECS task in ECS Cluster of Fargate Launch Type on each event 
	4. Task has a Task role, now it can access and get object from S3 and put the result in DynamoDB
2. Eventbridge can schedule to run a ECS Task in Fargate and batch process some data in S3. 
	1. Another example of serverless batch processing of our data.
3. ECS- SQS
	1. As the queue messages increase 
	2. We can have ECS Service Auto Scaling setup to launch new tasks to accomodate. 
4. Event Bridge Intercept Tasks related events 
	1. If a task is exited eventbridge receives a event 
	2. Trigger notification to SNS hence to admins 
	3. We can monitor lifecycle of tasks using Event bridge