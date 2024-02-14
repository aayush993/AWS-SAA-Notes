- or Global user base of an application
- We can avoid multiple hops over the internet 
- Use Global Accelerator to leverage Private AWS network ASAP
- Unicast IP vs Anycast IP (all servers having same IP, closest server)
- ==Request goes to AWS edge location(using Anycast IP) closest to user and then over AWS private network to the application.==
- ==2 Anycast IP created for your Application==

## Notes
1. Works with: EC2, ALB, NLB, Elastic IP, Public or private
2. Consistent Performance
	1. Intelligent routing to lowest latency 
	2.  Fast regional failover
	3. ==No issue with client cache== ( because IP don't change )
	4. Internal AWS network
3. Health Checks 
	1. performs for your applications
	2. makes your app global (failover in less than 1 minute)
	3. Great for DR
4. Security 
	1. Only 2 external IP for whitelisting 
	2. DDoS protection, [[AWS Shield]] 


## Global Accelerator vs CloudFront
- CloudFront 
	- Improves performance for cacheable content and Dynamic content (API Delivery and dynamic site delivery)
	- ==Content is served at edge==
- Global accelerator
	- for apps over TCP or UDP 
	- proxy packets at the edge to apps in AWS.
	- ==no cache, all req goes to apps==
	- Good for non HTTP USE: gaming, IoT, Voice Over IP
	- Good for HTTP : ==requiring static IP address, for deterministic, fast regional failover.==

## COST
running fees + data transfer fee

## Global Accelerator for Blue Green Deployments
- Global accelerator uses endpoint weights to determine traffic proportion to each endpoint.
- you can shift traffic gradually or at once between blue green application environments. 
- changes are effective within seconds
- Which is better than DNS solution as DNS resolvers are subject to DNS caching on client devices.