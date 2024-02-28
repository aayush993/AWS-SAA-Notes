- Upto 15 read replicas
- ==Within AZ, Across AZ, cross region.==
- ASYNC replication : Eventually consistent
- Can be promoted to their own DB
- ==***** Connection String must be updated in application to leverage read-replica***== 
- For read only use case and avoid load on main DB
- Each replica must be same size and resources as the main DB.

#### Network Cost
1. Within Region No cost
2. Cross Region fees.