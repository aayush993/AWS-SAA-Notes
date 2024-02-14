- For audit purpose, you can log all access to S3 buckets
- Any request, from any account, authorized/denied will be logged into another S3 bucket.
- That data can be analyzed using data analysis tool
- ==target logging bucket must be in same AWS region.==
- Specific log format.

#### Warning
- To avoid, Logging loop
- Do not set your logging bucket as the bucket you are monitoring

Each log is logged as an object.