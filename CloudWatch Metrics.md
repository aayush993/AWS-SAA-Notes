- CloudWatch provides metrics for every service in AWS 
- ==Metric== = variable to monitor (Eg: CPUUtilization)
- They belong to ==Namespaces==
- ==Dimension== - attributes of a metric ( eg: instance ID or environment..)
	- Upto30 per metric
- Metrics have timestamps 
- Can create dashboard of metrics 
- ==Custom metrics==: for ex: RAM 

## Metric Streams
- stream CW metrics to a destination 
	- near real time delivery 
	- low latency 
- Destination:
	- [[Kinesis Data Firehose]]
	- 3rd party: datadog, splunk, Dynatrace etc. 
- Option: Filter metrics to stream