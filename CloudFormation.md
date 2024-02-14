- It is a ==declarative== way of outline AWS infra for any resources. (most supported)
- CloudFormation template can have for example:
	- create sec group 
	- 2 EC2 instances using sec group 
	- S3 bucket 
	- ELB in front
- Creates all these for you and in the right order. 

### Benefits 
- Infra as code 
	- good for control 
	- changes can be reviewed as code. 
- Cost 
	- each resource of the ==stack==  is tagged with id so we can see how much full stack costs 
	- estimate cost with CloudFormation Template 
	- Saving strategy: In dev automate deletion of templates at 5 and recreation at 8 in the morning.
- Productivity 
	- create destroy infra on the fly
	- Automate diagram generation for your template 
	- Declarative programming (no need to worry about orchestration)
- No re-invent wheel 
	- Leverage existing templates 
	- Leverage docs
- Supports almost all services 
	- if not use "custom resources"

### Template is a yaml file you can upload or keep it in S3.
we can update the template as well after creating stack from it. 
Change set- what update to a template will do once we update it. 


[[CloudFormation StackSets]] 