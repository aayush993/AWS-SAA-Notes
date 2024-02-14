Characterized in Size, Throughput and I/O PS
Only SSD types can be used for boot (i+g)

#### Use Case
1. General Purpose SSD (Max 16000 IOPS)
	1. Cost effective 
	2. Low latency 
	3. Use: Boot volumes, virtual desktops(dev/test environment)
	4. 1GB - 16 TB
	5. gp3: Increase IOPS and Throughput independently
	6. gp2: size of volume and IOPS are linked (3IOPS / GB)
2. Provisioned IOPS (PIOPS) SSD: (Max 256000)
	1. Critical business applications with sustained IOPS required
	2. ==Great for DB workloads requiring storage perf==
	3. io1/io2 (4GB to 16TB)
		1. Max 32000 IOPS, for Nitro EC2 64000
		2. IOPS increase independent of size
		3. io2 more durable and more IOPS per GB than Io1 at same price
	4. io2 Block Express 4GB to 64TB
		1. ==sub millisecond latency== 
		2. Max 256000 IOPS. IOPS:GB -> 1000:1
	5. Supports [[EBS Multi-Attach]]
3. Hard Disk Drive:
	1. 125GB to 16TB
	2. st1: Throughput optimized
		1. Big data, data warehouse, log processing
	3. sc1: Cold HDD
		1. For infrequent access
		2. low cost important

Comparison [[References]] 