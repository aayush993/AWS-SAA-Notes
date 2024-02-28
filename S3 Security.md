1. User Based
	1. [[IAM Policies]]
2. Resource Based
	1. [[S3 Bucket Policies]]: Give cross account access to users
	2. Object Access Control List (ACL) - finer grain ( can be disabled)
	3. Bucket Access Control List ( ACL) - less common ( can be disabled)
		1. Grant access to group of users or accounts not specified users in other accounts

When can an IAM principal access S3 bucket:
	- User IAM permissions allow it 
	- OR resource policy allows it 
	- ==AND== There is no explicit ==DENY==


#### Encryption 
encrypt objects using encryption keys.
More on this later:
[[S3 Object Encryption]]
#### Scenarios
1. Public Access: Bucket Policy 
2. User Access - IAM Permissions
3. EC2 Access - IAM Roles
4. Cross Account Access - Bucket Policy
	1. lambda across account, set perm to S3 in IAM role for lambda. 
	2. Set perm to lambda in bucket policy of S3 as well.
	3. In same account only one perm and no deny is enough

#### Block Public Access Settings 
- Extra layer of settings 
- Prevent data leaks 
- ==Can be set at account level==
- we have to disable this if we want public access. only assigning policy won't suffice.

#### Giving Public Access
- add /* at the end of ARN as the policy applies to objects of the bucket

More [[IAM for S3 Object level vs bucket level permision]] 