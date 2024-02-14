
## S3 Events to multiple Queues
- for same combination: event type (eg: object create) and prefix (eg: images/) you can only have ==one S3 Event Rule==
- to send them to multiple SQS queus use fan-out

## SNS to S3 through KDF
![[Pasted image 20240126184230.png]]