- Move large data to and from.
	- ==Agent need: on prem/ other cloud to AWS== ( NFS, SMB, HDFS, S3 API...)
	- ==No agent need: AWS to AWS== (different storage services)
- Replication tasks ==can be scheduled ==hourly, daily weekly
- ==File permissions and metadata are preserved( NFS POSIX, SMB...==)
- Direct transfer into Glacier.
- S3 EFS FSx

![[Pasted image 20240126014203.png]]
![[Pasted image 20240126014134.png]]