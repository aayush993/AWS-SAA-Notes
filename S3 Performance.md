- S3 Auto scales to high request rates, latency 100-200 ms 
- at least 3500 PUT/COPY/POST/DELETE or 5500 get/head req/second per prefix in a bucket 
- No limits on number of prefixes.
- If you spread reads across prefixes, we can get 5500* number of prefixes req per second for GET.

#### Optimizing performance
1. Multi-Part Upload
	- recommended file >100mb
	- must file > 5GB 
	- parallelize uploads
2.  S3 Transfer Acceleration
	- for upload and download. 
	- transfer to edge location which forwards data to S3 bucket in target region 
	- compatible with multi part upload.
	- No charge for failed acceleration
1. S3 Byte Range Fetches- 
	- Parallelize GETs by requesting specific byte ranges 
	- better resilience in case of failures
	- ***Speed up downloads by req all the bytes in parallel***
	- ***retrieve only partial data ( for eg: head of file)***

## Review Notes
-----
### S3TA vs CloudFront 
- If object size is less than 1 GB consider CloudFront
- Other wise use S3TA.