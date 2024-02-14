- Objects have a key 
- Key = prefix + object name  (my_folder1/another_folder/my_file.txt)
s3://my-bucket/my_folder1/another_folder/my_file.txt
- No concept of directories. 
- Just keys with long name having slashes
- Object value is content of the body:
	- ==Max size is 5TB== 
	- More than 5 GB, must use "Multi-part Upload"
- Metadata: list of k/V pair - set by system or user
- Tags ( Unicode K/V pair - up to 10) - useful for security / lifecycle