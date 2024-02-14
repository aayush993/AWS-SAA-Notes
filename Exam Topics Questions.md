Q- Unpredictable access patterns and freq and infreq access 
A- Intelligent tiering
- S3 Intelligent-Tiering is the ideal storage class for data with unknown, changing, or unpredictable access patterns, independent of object size or retention period. You can use S3 Intelligent-Tiering as the default storage class for virtually any workload, especially data lakes, data analytics, new applications, and user-generated content.

Q- Create a graph comparing cost of EC2 in past 2 months and perform in depth analysis with least overhead
A-  Use cost explorer granular filtering 

[[AWS Billing and Cost Management]]

Q- CloudWatch dashboard sharing with least privilege
A- We can share dashboards and designate specific email addresses of people who can view the dashboard.
- share dashboard link publicly 
- Share dashboard in your account and specify thrid party SSO provider for dashboard access. 

Q- MS AD authentication with AWS SSO 
A- 
- 2 way trust for all AWS services (including SSO)
- 1 way for EC2, RDS, FSx
