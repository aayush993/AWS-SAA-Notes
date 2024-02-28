
1. On Demand
	1. Cost: Highest
	2. Recommended: short-term, unpredictable workloads
	3. Linux-win per sec, other per hour bill
2. Reserved Instance
	1. 72% discount on On-Dem
	2. Reserve specific attributes of instance (Instance Type, Region, Tenancy, OS)
	3. Payment- no, partial or all upfront
	4. Regional or Zonal
	5. Recommended: steady state apps
	6. Buy and sell reserved instances
	7. Option of Convertible Reserved Instance
		1. Less savings more flexibility
3. Savings Plan
	1. Same discount as RI
	2. Commit to certain usage ($10/hour for 1-3 years)
	3. Usage beyond billed on-demand
	4. locked at instance family & AWS  Region
	5. Flexibility Across other attributes.
4. [[Spot Instances ]]
	1. More discount 90%
	2. can lose at any point (current price > max spot price)
	3. Recommended: workloads resilient to failures.
	4. Not suitable for critical jobs or DB's
	5. ==Spot block can be used for upto 6 hours==
5. Dedicated Hosts
	1. Physical server for EC2's 
	2. Recommended: ==compliance, server bound software licenses.== 
	3. Purchasing Option: On-Demand, Reserved
	4. Most expensive
6. Dedicated Instance 
	1. Places your instance on ==hardware dedicated to you==.
	2. Less exposure to physical ports and underlying infra of physical server than Dedicated hosts
7. Capacity Reservation
	1.  Reserve On-demand instance capacity in specific AZ for any duration
	2. No discount, no time commitement,
	3. Recommended: to access capacity when needed. Short term, uninterrupted workloads
	4. Use With Reserved or Savings plan for discount.


#### When should you use Savings Plans, EC2 RIs and On-demand capacity reservation?
- Saving plan - reduce bill by committing to 1-3 yrs term. just like RIs
- On Demand Cap Reservation - gives confidence in ability to launch 
	- for any duration 
	- independent of Saving plan and RI
	- can also club with them.