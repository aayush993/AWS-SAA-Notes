- Data Lake = Central place for all your data for analytical purposes 
- Fully managed service
- ==Makes easy to setup data lake== 
- Discover, cleanse, transform and ingest data into your dtaa lake 
- Automated many complex manual steps 
	- collect 
	- cleanse
	- move 
	- catalog data 
	- and DE-DEPULICATE (using ML transforms)
- Combine ==structured and unstructured data== 
- Out of box source blueprints : S3, RDS, RDBMS & NoSQL
- ==Fine grained access control of your apps (row and column level)==
- built on top of AWS Glue
![[Pasted image 20240129182202.png]]

## Why Lake Formation 
We have data in different sources like S3, RDS and Aurora. 
We need to runquery on Athena and create quicksight dashboards and set access control for users accessing that.
We can set up access control for each of these services which will be complex. 
Or we can just ingest data in Data lake 
and set Column-level security.