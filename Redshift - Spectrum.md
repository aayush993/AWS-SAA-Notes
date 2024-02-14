- Data is in S3 
- we dont want athena as query is intense 
- Now, ==we already have a Redshift cluster available==
- We query our cluster and then submitted to thousands of Redshift spectrum nodes which performs the query on S3. 

>Leverage more compute power without loading data in S3.

![[Pasted image 20240129210810.png]]