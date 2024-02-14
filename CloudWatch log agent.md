
## Logs for EC2
- By default, logs from EC2 are not send into CloudWatch 
- Run CloudWatch Log agent to send logs to CloudWatch
- Make sure IAM permissions are correct 
- Same way can be setup== for on-prem servers==

### CloudWatch Logs Agent 
	- old version 
	- only send logs to CloudWatch Logs 

### CloudWatch Unified Agent 
 - ==Collect system level metrics== 
 - ==Collect logs== 
 - centralized config from SSM Parameter store 
 - What metrics we can collect ?
	 -  CPU 
	 - Disk Metrics 
	 - RAM 
	 - Netstat
	 - Processes 
	 - Swap space 
- Default metrics for EC2 - disk, CPU, network ( high level)
	- For more granularity use Unified agent