- Fully managed, HA
- seamless ==in-memory cache for DynamoDB== 
- ==Solves read congestion by caching==
- ==Microseconds== latency for cached data
- No app logic change required
- 5 minutes TTL default

## DAX vs ElastiCache
- DAX is for
	- Objects cache 
	- Query & scan cache 
- ElastiCache
	- To cache big computational result 
	- Aggregation result

