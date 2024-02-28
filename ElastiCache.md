Amazon ElasticCache
- Managed Redis or Memcached
- ==Cache/In-memory DB:== High performance, low latency
- AWS takes care: OS maintenance, patching, optimizations, setup, config, monitoring, failure recovery and backups.
- ***Using ElastiCache involves heavy code changes in Apps***

Use case:
- Make app stateless. User Session Data
- reduce load off the DB for read intensive workloads. DB Cache

> Cache's must have an invalidation strategy to have most current data in cache.

#### Redis VS Memcached

In summary, Redis is for HA, Backup restore, durability while. 
memcached is where no problem to loose your data, partitioned

![[Pasted image 20240113004211.png]]

#### Cache Security
IAM policy are only for AWS API level security.
1. Redis:
	1. IAM Authentication
	2. Redis AUTH
		1. Set password/token when you create redis cluster
		2. Extra security on top of sec groups 
		3. Supports SSL in flight encryption
2. Memcached:
	1.  Use Username password for authentication
	2. Supports SASL based authentication(advanced)

#### Cache Patterns
1. Lazy loading: hit and miss. all read data is cached. cache can become stale.
2. Write-Through: Update data in cache when written to DB (no stale data)
3. Session Store: store temporary session data (using TTL features )

#### Redis Sorted Sets Use case for Gaming Leader Boards
Redis Sorted sets guarantee both uniqueness and element ordering. 
Each time new element added, it's ranked in real-time and then added in correct order.

## Notes
1.  It's HIPAA compliant
2.  Redis for geospatial data, sorted sets and many other HA features and transactional support 
	- Memcached for multi threaded architecture.
![[Pasted image 20240218112624.png]]