## Serverless Thumbnail creation 
1. Image uploaded in S3 
2. triggers lambda 
3. Creates a thumbnail and saves in S3
4. Pushes metadata in DynamoDB

## Serverless CRON Job
- CRON jobs are like scheduled jobs which are run from an EC2 instances 
- rest of the time EC2 is idle. 
- We can have a Cloudwatch event to be triggered as per schedule and it triggers Lambda 
- This will result in serverless CRON Job.