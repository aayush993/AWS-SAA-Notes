- AWS managed NAT Instances. 
- High bandwidth, High availability
- ==No administration==
- NATGW is created in ==specific AZ==, ==uses an Elastic IP==
- Cant be used from EC2 from same subnet ==only from other subnets==
- ==Requires an IGW== 
- 5GBps bandwidth - auto scaling to 100Gbps
- No sec groups to manage/required

## Works like 
- Update route table of private subnet to route traffic to NAT gateway 
- NAT gateway sends to IGW

## NAT and HA
- Resilient in an AZ
- Create multiple NAT, each in an AZ for fault tolerance 
- If an AZ fails, no cross AZ Failover required as EC2 in that AZ is inaccessible.

