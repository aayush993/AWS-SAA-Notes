Load balancers forward traffic to downstream systems
 - Spread load 
 - Expose Single DNS to your app
 - Seamless failure handling 
 - Regular health checks
	 - done on a port and a route 
	 - if response is not 200, unhealthy

ELB is a managed LB.
- AWS gives only few knobs for configuration 
- AWS responsible: maintenance, upgrade and High availability 
- Different types: [[CLB]], [[ALB]], [[NLB]], [[Gateway Load Balancer]] 
- Recommended to use new gen 
- can be setup as internal or external facing.
- [[Bound to Region]] 
-  - [[SSL Terminate]] for websites 
 - separate public private network
 - enforce stickiness with [[Sticky sessions]]
 - HA across zones, distribute evenly across zone [[Cross Zone Load Balancing]]
 - Time to complete request while instance is de-registering [[Connection Draining]] 


#### Costs more
Than your own LB but very less effort to setup. 

#### Integrated with AWS
[[EC2]], [[ASG]], [[Amazon ECS]]
[[AWS Certificate Manager]], [[CloudWatch]]
[[Route 53]], [[AWS WAF]], [[AWS Global Accelerator]]

#### Security
Source in LB SG can be anywhere.
Source in app can be only LB SG. 
Extra security.
