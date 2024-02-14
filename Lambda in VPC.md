- Lambda by default is launched outside your own VPC 
- cant access resource in your VPC
- You must define VPC ID, subnets and sec groups 
- Lambda will create an ENI In your subnets with these.
- Using this we can access resources in your VPC

## Lambda with RDS Proxy 
- If lambda access RDS directly it will load the DB alot
- Hence, [[RDS Proxy]]
- And it can only be accessed within VPC, never publicly.
![[Pasted image 20240131213744.png]]