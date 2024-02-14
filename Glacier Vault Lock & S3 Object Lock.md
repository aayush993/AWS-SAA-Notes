
#### Glacier Vault Lock
- To Adopt WORM (Write Once Read Many) model.
- Create a vault lock policy 
- Lock the policy for future edits.
- Helpful for compliance and data retention.

## S3 Object Lock
- ==versioning must be enabled==
- To adopt WORM
- Block an object version deletion for a specified amount of time 
- Retention mode:
	- Compliance: 
		- Object versions can't be overwritten or deleted by any user including root user
		- Object retention modes can't be changed and retention periods can't be shortened
	- Governance: 
		- Most user can't overwrite or delete an object version or alter its lock settings 
		- Some users have special permissions to change the retention or delete object
- Retention period: protect the object for a fixed period, it can be extended. 
- Legal Hold: 
	- Protect the object indefinitely, independent from retention period
	- can be freely placed or removed using S3:PutObjectLegalHold IAM permission.
While enabling Locking on a bucket you can set default retention and specfiy retention period only 

On a object you can specify retention date as well