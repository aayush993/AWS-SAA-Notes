Application Load Balancer (v2)
- Layer 7(HTTP) Load Balancer
- Load balancing to multiple applications
	- across machines (target groups, can be multiple)
	- same machine (containers)
- Support for HTTP/2 and websocket 
- ==Support for redirect HTTP to HTTPS==
- Port mapping feature to redirect to dynamic port in ECS
- CLB needs multiple LB per application bases. Here not needed.
- Health checks at target group level

#### Routing Tables to different target groups
- Route based on path in URL. 
- based on hostname in URL
- based on query string, headers

#### Great fit for
micro services an container based applications

#### Target Groups
- EC2 Instances (ASG managed) - HTTP
- EC2 Tasks (ECS managed) - HTTP
- Lambda functions - HTTP req converted to JSOn EVENT 
- IP addresses: must be private

#### Facts
- Fixed hostname with your ALB (XXX.region.elb.amazonaws.com)
- app servers dont see client IP:
	- IP of client is inserted in header X-Forwarded-For
	- Port - X-Forwarded-Port
	- Proto- X-Forworded-Proto