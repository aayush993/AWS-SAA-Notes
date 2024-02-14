- take advantage of Unused EC2 in AWS
- 90% discount 
- used for fault tolerant and flexible application
- Not great for critical workloads.
- [[Spot Fleets]]

#### How to Request one
- Define max spot price 
- get it if max spot price > current price 
- if current price > max spot price - terminate or stop your workloads
- 2 minutes grace on loosing spot
Also,
- ***Spot Block*** during specified time frame (1-6hours)
- rarely, spots are reclaimed.

#### Cancelling Spot Instances
- Cancel request then terminate spot instance as well
- Can only cancel open, active or disabled requests.
![[Untitled.png]]