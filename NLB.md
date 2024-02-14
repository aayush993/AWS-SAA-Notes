Network Load Balancer (v2)
-- 
- Layer 4
- allow to:
	- Forward TCP& UDP traffic to your instances.
	- Handle millions request per seconds 
	- less latency ~ 100ms (vs 400ms for ALB)
- ***One static IP per AZ, supports assigning Elastic IP*** , Used for Whitelisting IP
- Use: Extreme performance, TCP UDP traffic
- Not in free tier


#### Target Groups 
- EC2 Instances 
- Private IP address
- ALB: when we need fixed IP address with many HTTP rules of ALB
- Health checks support TCP, HTTP and HTTPS protocol