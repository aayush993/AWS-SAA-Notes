IAM policies applied to OU or Accounts to restrict ==Users and roles==. (Does not effect groups)
	- ==Not applied to management account== (full admin power)
	- Must have explicit allow - (default DENY)

## SCP Hierarchy 
- If there is one DENY in your policy. It means Deny.
- Management account no deny applied.
- Ex:
![[Pasted image 20240131124713.png]]

SCP Examples:
![[Pasted image 20240131124809.png]]


## Review Notes 
### SCP Does not effect 
- resource based policies.
- management account 
- Does not effect service linked roles.

A service-linked role is a unique type of IAM role that is linked directly to an AWS service. Service-linked roles are predefined by the service and include all the permissions that the service requires to call other AWS services on your behalf.