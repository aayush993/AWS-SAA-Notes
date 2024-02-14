- collect, process and analyze streaming data in real-time
- real time data ingestion: Application logs, metrics, website clickstreams, IOT telemetry data

1. [[Kinesis Data Streams]] : capture, process and store data streams
2. [[Kinesis Data Firehose]]: load data streams into AWS data stores
3. [[Kinesis Data Analytics]] : analyze data streams with SQL or Apache Flink
4. Kinesis Video streams: capture, process and store video streams

## Diff KDS vs KDF
- KDS
	- Streaming service for ingest at scale 
	- Write custom code for consumer/ producer
	- Real-time 
	- Manage scaling 
	- Data storage: 1 -365 days
	- Supports replay
- KDF
	- Load streaming data into Destinations
	- Fully managed 
	- near real-time 
	- Auto scaling 
	- No data storage 
	- No replay