- Fundamental to network security in AWS.
- ==contain allow rules.== 
- inbound and outbound rules. 
- refer by IP or Security group
- Specify Authorized IP Ranges & [[Port]] Range + Protocol.

#### Facts
1. Can be attached to multiple instances 
2. Regional + VPC specific. 
3. Lives outside EC2
4. ***BP***: maintain separate SG for SSH access.
5. If app gives time out - SG issue.
6. Connection refused error - app error
7. Inbound traffic - blocked by default
8. Outbound - allowed default


Add rules to allow traffic to the instance. 
like SSH, HTTPS or ICMP access.

## Source and Destination
- IPv4 - IP or set of IP in CIDR notiation 
- IPv6 
- prefix list ID
- SECURITY GROUP