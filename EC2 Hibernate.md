- Ram state preserved 
- Instance boot is faster
- Under the hood: OS not stopped or restarted, ram is written in root EBS. 
- root EBS must be encrypted
- Use
	- Long running process
	- Long Initialization applications

#### Conditions
- root EBS encrypted, No instance store and large
- RAM < 150 gb
- Instance not bare metal
- On-Demand, Reserved and spot support 
- Instance Family: C3, C4, C5, I3, M3, M4, R3, R4, T2, T3
- Hibernate < 60 days
- ==Cannot be enabled once Instance is launched.== 