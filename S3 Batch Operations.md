
- Perform bulk operations on existing S3 objects with a single request.
- Eg:
	- Modify object metadata & properties 
	- Copy objects bw S3 buckets 
	- ***==Encrypt un-encrypted objects==***
	- Modify ACLs, tags
	- Restore objects from glacier.
	- Invoke Lambda function to perform custom action on each object.
- A job consist of list of objects and actions to perform and optional params. 
- S3 batch operation 
	- Retries,
	- tracks progress, 
	- sends completon notifications
	- generate reports 
- ==Use S3 inventory to get object list and use S3 select to filter your objects.== 
![[Pasted image 20240124182417.png]]