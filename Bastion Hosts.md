- Can be used to access private hosts. 
	- can ssh to bastion host from internet 
	- then ssh from bastion host to our private host using private IP use key pair.
- host with name bastion host is ==created in public subnet== 
- It has it's own Security group 
	- must allow inbound internet traffic on port 22
	- We can limit CIDR's to for eg: your corporation only for more security.
- Sec group of Private EC2 instance - 
	- should allow sec group of bastion host or
	- Private IP of bastion host