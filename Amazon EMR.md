- Elastic Map Reduce 
- Helps in creating ==Hadoop clusters (Big Data)== to analyze and process vast amount of data.
- can be ==made of 100s of EC2 instances== 
- comes ==bundles with Big data tools== like Apache Spark, HBase, Presto, Flink 
- EMR takes care of all provisioning and config
- ==Auto-scaling and integrated with spot-instances==

Use: data processing, machine learning, web indexing, big data

## Node Types & purchasing 
- Master node 
	- Manage cluster, coordinate, manage health 
	- Long running 
- Core node
	- Store data run tasks 
	- long running 
- Task node ( optional)
	- run tasks
	- usually spot
- Purchasing 
	- On-demand: reliable, predictable, won't be terminated - for master nodes 
	- Reserved (min 1 year): cost savings (EMR will auto use if available)
	- Spot 
- Can have long running cluster or transient cluster