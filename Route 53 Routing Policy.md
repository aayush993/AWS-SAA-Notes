It defines how Route 53 responds to DNS Queries. It does not route.,

1. Simple- 
	- Route traffic to single resource. 
	- specify multiple values in same record. 
	- client chooses a random one. 
	- ==When Alias enabled, specify only one AWS resource.== 
	- ==Can't be associated with health checks==. 
2. Weighted:
	1. Control % of traffic going to each specific resource. 
	2. % is calculated by weight assigned to each resource divided by sum of all weights. 
	3. Weights total is not 100.
	4. Add multiple DNS records with same name and type. 
	5. Health checks: yes
	6. 0 weight to disable resource. 
	7. if all have 0 then equal traffic. 
	8. Use: Load balancing between regions, testing new applications.
3. Latency Based:
	1. Use same name and policy type. 
	2. specify region along with the IP
	3. Routed based on lowest latency
	4. Health checks: yes. Failover yes
4. Failover (Active-Passive):
	1. using [[Route 53 - Health Checks]]
	2. Create Two A records with policy failover. 
	3. Record type selected as Primary/secondary.
	4. Health check need not to be associated with secondary.
5. Geo-Location:
	1. Multiple A Records with same name and Type geolocation. 
	2. Specify a country for which IP returned should be the value. 
	3. health check- yes optional
	4. ==create default record. for no match of location.==
	5. Use: Website localization, restrict content distribution, load balancing. 
6. Geo-Proximity:
	1. Route traffic based on geo location of users and resources using biases. 
	2. To expand (0-99) more ==bias==
	3. To shrink (-1 to -99) less bias
	4. Resource can be AWS or Non-AWS (Longitude/latutude)
	5. Route 53 Traffic flow feature
7. IP Based:
	1. For particular CIDRs route to a particular resource. 
	2. If client is part of some CIDR it will get that resource. 
	3. Use: Optimize performance, reduce network costs. 
8. Multi-Value:
	1. Add multiple same name and type A records. 
	2. associate each with health checks.
	3. Routing traffic to multiple resources. return only healthy resources. 
	4. Up to 8 health record returned for each multi-value query
	5. For client side load balancing.