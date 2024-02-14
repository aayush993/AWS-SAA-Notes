- After a message is polled by a consumer- it becomes invisible to other consumers.
- Default- 30 seconds.
- After this timeout it again becomes visible
-![[Pasted image 20240126173849.png]]

- If message is not processed in Message visibility timeout, it will be processed twice. 

## More time for processing can be requested by consumer 
ChangeMessageVisibility API 

## Set Message Visibility timeout cautiously
- Too high can cause delay in re-processing, in case of consumer crash
- Too low can cause duplicates.