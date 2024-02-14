- Allow resources in a VPC to connect to internet 
- scales horizontally and is HA and redundant. 
- created separately from VPC. 
- ==One VPC <-> one IGW==
- Internet gateway alone do not provide access to Internet 
- Need to edit Route tables as well.

## Creating IGW 
- once created
- attach it to a VPC
- Create a [[Route table]] and edit them and attach to our subnets.