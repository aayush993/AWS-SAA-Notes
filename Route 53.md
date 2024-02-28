Amazon Route 53 is a Highly available, scalable, fully managed and authoritative [[DNS]] 
- Authoritative = customer can update DNS Records.
- is also a Domain Registrar. 
- [[Route 53 - Health Checks]] of your resources. 
- Only AWS service: 100% SLA
- 53 is traditional DNS port

#### Route 53 Records
- Helps you define route for a traffic of a domain 
- Each record contains:
	- Domain/subdomain name: eg: example.com
	- Record Type:  eg: A, AAAA
	- Value: eg: 12.34.56.78
	- [[Route 53 Routing Policy]]: how Route 53 respond to queries. 
	- TTL : Amount of time record cached at DNS resolvers.
- Route 53 supports following DNS record types:
	- (must know) A/AAAA, CNAME, NS
	- CAA, DS,MX,NAPTR, PTR, SOA, TXT,SPF,SRV

#### Record Types
1. A - maps a hostname to IPv4
2. AAAA - maps a hostname to IPv6 
3. CNAME - maps a hostname to another hostname 
	1. Target is a domain name which must have an A or AAAA record
	2. Can't create a CNAME record for the top node of DNS namespace (Zone Apex). To do that [[Alias Records]]
	3. Example: you cant create for example.com, but www.example.com can be created.
4. NS - Name Servers for the Hosted Zone
	1. Control how traffic is routed for a domain.
	2. Anytime we register a domain IN ROUTE 53 this will already be there. 

#### Hosted Zones
Container for records that define how to route traffic to a domain and its subdomains. 
- Public Hosted zone - for internet clients
- Private Hosted Zone - one or more VPCs
	- For using Private hosted zones in VPC. 
	- DNS hostnames and DNS resolutions are required settings to be enabled. enableDNSSupport and enableDNSHostnames
	- Not enabled by default if you dont use wizard to create VPC
	- If we have a Resolver rule call to DNS in our network and there is a conflict with our private hosted zone DNS. Resolver rule takes precedence
> If your domain name is registered in Route 53, you will see a hosted zone for your Domain name. 

#### Records TTL
- High TTL - 24 hours
	- Less traffic on Route 53 
	- stale records on DNS resolvers
- Low TTL: 60 sec
	- More Traffic on Route 53 (money)
	-  Records are outdated for less time 
	- easy to change records.
> Except for Alias record TTL is mandatory for all record types. 




