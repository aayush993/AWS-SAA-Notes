- Can move objects manually or using lifecycle configurations to storage classes.
1. Durability 
	1. High Durability : same for all storage classes 
2. Availability 
	1. Depends on storage class.


#### S3 Standard - General Purpose
1. 99.99% available 
2. freq accessed data
3. low latency and high throughput.
4. Sustain 2 concurrent facility failures
5. Use case: big data analytics & gaming apps, content distribution 

#### S3  Infrequent Access
1.  less freq access, but ==rapid access when needed==
2. Lower cost than standard
	1. Standard IA 
		1. 99.9% AVAILABLE 
		2. USE: DR, Backups
	2. One Zone - IA 
		1. High Durability 99.9999999999% in a single AZ
		2. 99.5% available
		3. Use: Secondary copy of data or on-prem data, data we can recreate.

#### Glacier Storage Class
- Low cost meant for archiving / backup 
- Pricing = storage + retrieval
1.  S3 Glacier Instant Retrieval 
	1. Millisecond retrieval, great for data accessed once a quarter
	2. Minimum storage duration of 90 days
2. S3 Glacier Flexible Retrieval 
	1. Expedited ( 1 to 5 minutes), Standard ( 3 to 5 hours), Bulk ( 5 to 12 hours) --- free
	2. Minimum storage duration of 90 days
3. S3 Glacier Deep Archive -- long term storage
	1. Standard ( 12 hours ) , bulk ( 48 hours)
	2. Minimum storage 180 days

#### Intelligent Tiering 
- Small monthly monitoring and auto- tiering fee
- No retrieval charges 
- moves objects automatically between access tiers based on usage
1. Freq Access tier(auto) : default tier
2. IA tier (auto): not accessed for 30 days
3. Archive Instant Access tier (auto): not access 90 days
4. Archive Access tier  (optional) - configurable 90 to 700+ days
5. Deep Archive Access Tier (optional)- config from 180 to 700+ days

[[References]] 

## Review Notes 
- Transitions 
	- min 30 days in standard before going to IA or one Zone IA 
	- min 30 days in IA or 1Z IA before going further
	- Supported transitions one way
		- Standard - > IA -> Intelligent Tier -> 1Z IA -> Glacier Instant -> G Flex -> G Deep
		- Not supported - 1Z IA to G instant
	- Larger objects preferred 
	- Rule precedence - 
		- Permanent deletion over transition 
		- Transition over delete marker creation
		- Prefer Glacier, from Glacier flex, IA or 1Z IA