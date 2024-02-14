- Supported for io1/io2
- same EBS to multiple EC2 (16 Instances Max)
- within same AZ only
- Application manage concurrent read write
- Use: Achieve HA for clustered linux application(ex: teradata)


#### Must use file system that's cluster aware (not XFS, EXT4, etc..)