#### IAM Conditions 
- They apply to policies in IAM (IAM Policy, bucket policy, resource policy, endpoint policy)
- Below policy have a prefix which signifies to what it is applied to. aws = globally, ec2 is only to ec2
- aws:SourceIp - Restrict client IP ==from== which AWS API calls are being made.
- aws:RequestedRegion  - restrict regions to which API calls are made ==to==
![[Pasted image 20240131132516.png]]
- ec2:ResourceTag - restrict based on tags
- aws:MultiFactorAuthPresent: to force MFA
![[Pasted image 20240131131947.png]]

