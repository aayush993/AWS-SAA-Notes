- Generate a pre-signed URL using S3 console, AWS CLI or SDK 
- URL Expiration
	- S3 Console - 1min upto 720 mins (12hours)
	- CLI- configure using --expires-in (in seconds, default 3600 secs, max 604800 sec ~168 hours)
- Using a pre-signed URL we inherit permissions of user who generated the URL for GET/PUT
- Ex:
	- Allow only logged-in user to download a premium video from S3 
	- Allow an ever-changing list of users to download files by generating URL's dynamically
	- Allow temporary access, to user for upload a  file at a precise location.