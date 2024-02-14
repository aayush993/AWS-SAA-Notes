- Principal Behind Multi-Region 
	- We have a key in a region = Primary Key 
	- then in all the other regions, we have Replica Key 
	- All Primary and Replica Key has same ID.
	- eg- arn:aws:kms:us-west-2:111122223333
	- the region part can vary though.
- They ==can be used interchangeably ==(Encrypt in one region, decrypt in another)
- ==auto rotation can be done==
- No need to re-encrypt or cross region API Calls.

- Not Global (Primary+replica)
- Each Key is managed independently 
- Use: Global Client side encryption, global DynamoDB, Global Aurora
- Not recommended until special use cases.

## Special Usecases
1. Client side encryption for some attributes stored in Global DynamoDB.
1. ![[Pasted image 20240201182316.png]]
2. Client Side encryption for Global Aurora
![[Pasted image 20240201182439.png]]