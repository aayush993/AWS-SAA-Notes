JSON Documents.
Define [[IAM Permissions]]


### Policy Inheritance 
1. User inherit group policy (all it's groups)
2. User can also have ==inline policy==

### Policy Structure
1. Version: Policy language version. Always same as image.
2. Id: optional
3. Statement: a list.
	1. Sid: Optional
	2. Effect: Allow/ Deny
	3. Principal: account/user/role
	4. Action: list of actions permitted 
	5. Resource: List of resource action applied to.
	6. Condition: optional, to make the policy conditional
!![[Pasted image 20240111225001.png]]
