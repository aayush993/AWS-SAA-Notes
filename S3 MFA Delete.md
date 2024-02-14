- Extra protection for important S3 operations 
- Required for :
	- permanently delete an object version 
	- Suspend versioning on the bucket 
- Not required for:
	- Enabling versioning 
	- LIST deleted versions
- ==To use MFA delete, versioning must be enabled on the bucket.== 
- ==Only bucket owner (root account) can enable/disable MFA delete==

We can do it by CLI, use root Access keys. 
pre-requisite- MFA device must be setup already. 