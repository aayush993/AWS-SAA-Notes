- Allows to start a secure shell on your EC2 and on-prem servers 
	- uses a SSM Agent on EC2 
- No SSH access required, no bastion hosts, no SSH keys 
- No port 22 needed 
- Hence., more ==secure== 
- Supports Linux, Mac, Win
- Send ==session log== to S3 or CloudWatch Logs

## Setup 
1. While creating EC2, create a role with a profile to be managed by SSM. 
2. System Manager > Fleet Manager >  Your EC2 will appear here. 
3. Go to session manager, start a session.
4. Gives you a secure shell.