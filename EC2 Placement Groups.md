Strategies for placing EC2 Instances:
1. Cluster
	1. Low latency 
	2. Same Rack and Same AZ
	3. 10Gbps NW
	4. High risk
	5. Use: fast network -low latency 
2. Spread
	1. Span across AZs
	2. 7 instances per AZ per placement group
	3. Instances on diff physical HW
	4. reduced risk
	5. Use: max HA, critical applications
3. Partition
	1. Span across multiple AZs in the same region
	2. 100s of Instances per partition
	3. 7  partitions per AZ
	4. Each partition different rack 
	5. EC2 instance have access to partition info as metadata
	6. Use case: GDFS, HBase, Cassandra, Kafka

![[Pasted image 20240112132738.png]]
![[Pasted image 20240112132748.png]]![[Pasted image 20240112132756.png]]