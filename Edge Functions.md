- Modern applications need customization at the edge 
- Edge Functions 
	- Code written and attach to CF Distributions 
	- Runs close to users to minimize latency 
- Two Types 
	- [[ CloudFront Functions]] : Lightweight functions for ==viewer req and response==
	- [[Lamda@Edge]]: Lambda function for ==viewer and origin req/response==
- Serverless, deployed ==globally== 
- Use: customize CDN  content
	- Website security and privacy 
	- Dynamic Web app at the edge 
	- SEO
	- Intelligently Route across origins and DC
	- Bot mitigation at edge 
	- Real-time Image transformation 
	- A/B Testing
	- User Authentication and authorization 
	- User prioritization 
	- User Tracking
- Pay for what you use


## Look at it for difference
![[Pasted image 20240128193138.png]]

## Use case diff
- CloudFront Functions 
	- Cache Key Normalization 
	- Header manipulation 
	- URL redirects 
	- Req authentication and authroization 
- Lambda@Edge 
	- Longer execution time 
	- Adjustable CPU or memory 
	- code can depend on 3rd party libraries 
	- Network access to use external services 
	- File system access or access to request body