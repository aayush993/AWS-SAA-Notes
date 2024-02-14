As public IP changes we need a fixed IP. 
- Reserves a public IP 
- remain with you until you delete it. 
- detach and attach to any instance
- 5 IP / Account (can request more)
- Charged when not in use. 

#### Use case:
mask instance failure. 
remap IP to another instance. 

#### Avoid Using
- Poor architecture decision
- Use a public IP and attach a DNS
- Or use load balancer and Use Public IP.