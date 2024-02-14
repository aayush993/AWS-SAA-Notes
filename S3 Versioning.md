- Version your files in S3 
- enabled at bucket level 
- overwrite will change the version 
- Best practice - to version 
	- ==Protect - unintended deletes==
	- Easy roll back 
- Any file not versions ==prior to enabling versioning - null== 
- ==Suspending versioning does not delete - previous versions.==
- cannot be disabled once enabled only suspending.

#### Deleting 
- Enabled version - delete a version - permanent delete
- Disabled version - delete marker - version persists.
