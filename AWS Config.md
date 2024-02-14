- Helps in auditing and ==recording compliance== of AWS resources. 
- ==Record configurations and changes over time.== 
- Eg: we can know if any of our buckets have public access
- We can create SNS  alerts fore any changes 
- [[Bound to Region]] 
- Can be ==aggregate across regions and accounts==
- Option to store ==config data into S3 and analyze with Athena==

## Config Rules 
- Can use AWS Managed rules (over 75)
- can make custom config rules (defined in AWS lambda)
	- ex: evaluate if each EBS is of type gp2
- Rules can be evaluated/triggered:
	- For each config change 
	- or at regular intervals
- AWS Config rules does not prevent actions. Just for compliance

## Pricing
- no free tier
- $0.003 per config item recorded per region 
- $0.001 per config evaluation per region 
- ==can be costly very fast==

## Config resource 
1. View compliance of resource 
2. View config changes over time 
3. View API calls for the resource (leverage CloudTrail API calls)

## Remediations 
- Do some automations for non compliant resources. 
- Using ==SSM Automation Documents==
	- Use ==AWS== Managed Automation Documents 
	- Create ==custom== Documents 
		- Tip: these documents can invoke Lambda 
- Remediation ==retries up to 5 times==

## Notifications 
- Use eventbridge to trigger notification when AWS resource is non compliant 
	- then further send to SNS, SQS, Lambda ...
- notify SNS, use filtering or filter at client side

## How to Setup One:
- Setup a AWS Config 
- Specify what to record
	- everything or specfic 
- where to store? : S3
- notify or not ?
- What rules to apply 
	- for eg: on sec group restricted-ssh
	- For each rule we can specify remediations using documents
- Once created we can checkout our resources.
	- As per rules we can see their compliance status 
	- There will be a resource timeline for each resource. 
- Now if i change my resource, evaluation will be triggered for the resource
- And it will check the compliance