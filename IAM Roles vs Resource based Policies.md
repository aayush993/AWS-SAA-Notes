#### Two ways for granted cross account access:
1. Attaching a resource based policy : like S3 bucket policy
2. Creating role with permission to resource and then User can assume that role. 

#### Difference in these two approaches 
1. When you assume a role (user, app service), you give up your original permissions and take the permissions assigned to the role.
2. While for resource based policy, principal can retain his permissions.
3. Ex: User in Account A needs to scan DynamoDB in account A and put result in S3 in account B.
4. Supported by: S3, SNS, SQS.

## Helps in EventBridge Security 
- when rule runs they need permission on targets 
- Resource Based policy : lambda, SNS, SQS, CloudWatch Logs, API Gateway...
- IAM Role: Kinesis stream, Systems Manager Run Command, ECS Task...
![[Pasted image 20240131134009.png]]