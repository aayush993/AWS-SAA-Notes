- Used ==to trigger notification for any metric== 
- Various options : sampling, %, max, min 
- States:
	- OK 
	- INSUFFICIENT_DATA
	- ALARM
- Period 
	- Length of time to evaluate a metric 
	- High resolution custom metrics: 10 sec, 30 sec or multiples of 60 sec

## Alarm Targets 
- 3 main targets 
	- EC2 Action - STOP, TERMINATE, REBOOT, RECOVER 
	- EC2 Auto scaling action - Trigger scale action 
	- Send Notification action - To ==SNS== - from there anything 

## Composite Alarms 
- Combine multiple alarms monitoring single single metrics. 
- Use AND and OR conditions 
- reduce "alarm noise"

## EC2 Instance Recovery
- Status check 
	- Instance status - EC2 VM check 
	- System status - underlying hardware check
- Recovery: Get same Public, private, Elastic IP , metadata, placement group


## Notes
- Alarms for CloudWatch Logs : Metrics Filter 
- Test Alarms and notifications, set alarm state to Alarm using CLI command.