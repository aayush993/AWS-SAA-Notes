Moving objects can be automated using lifecycle rules.

1. **Transition Actions:** configure objects to transition to another storage class
	1. Like move to IA after 60 days 
	2. move to glacier after 6 months for archival 
2. Expiration actions - configure objects to expire after some time
	1. Access log files can be set to delete after 365 days
	2. or delete old version of files 
	3. delete incomplete multi part uploads 

> Rules can be created for a prefix or object tags. 

#### S3 Analytics 
	- Gives csv report
- Helps you decide when to transition objects to right class. 
- Recommendation for Standard and Standard IA 
	- Does not work for one zone IA or glacier
- Report is updated daily 
- 24 to 48 hours to start seeing data analysis. 
- Good first step to put together lifecycle rules or improve them.