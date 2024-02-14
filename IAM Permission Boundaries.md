- Advanced feature
- We can set a boundary to restrict a IAM users and roles ==(not for groups)==

## Can be used with SCP
- Used with [[AWS Organizations Service Control Policies]]
- ==Intersection of SCP x Permission Boundary x Identity based policy==
Use case:
- delegate responsibility to non admin within their permission boundaries ex: create IAM user
- Allow developers to self assign policies while making sure they cannot escalate
- To restrict specific user

## How IAM Policy is Evaluated
Only if all this works together and there is no particular deny. 
![[Pasted image 20240131135048.png]]