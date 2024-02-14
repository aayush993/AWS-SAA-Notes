- NACL is stateless and Sec group is stateful
- NACL operates at subnet level and sec group at instance level 
- Applies to all EC2 in that subnet and sec group to that instance 
- ==First rule wins== and ==sec groups all rules== are evaluated before access granted 
- ==Allow and deny rules, Sec group has only allow rules==

![[Pasted image 20240204230131.png]]

## NACL 
- are like firewall, control traffic to a subnet 
- One NACL per subnet.
- ==New subnet assigned Default NACL==
- NACL Rules 
	- have a number (1-32766) - lower no high precedence 
	- last rule is * It denies the request in case no match 
	- AWS recommends adding rule increment in 100
- Newly created NACL deny everything
- Great for blocking specific IP address at subnet level 

## Default NACL
- Accepts everything In and Out. 
- Do Not modify default NACL.

## NACL with [[Ephemeral Ports]] 
![[Pasted image 20240204231322.png]]
![[Pasted image 20240204231533.png]]