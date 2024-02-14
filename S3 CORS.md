- Cross Origin Resource Sharing (CORS)
- Web browser based security mechanism to request objects from other origin while visiting main origin. 
- Request wont be full filled unless other origin allows for the requests using CORS headers.
- ex: Access-Control-Allow-Origin
- For any client making cross origin request on our S3 bucket, CORS headers have to be enabled.
- allow for specific or all origins 
-![[Pasted image 20240124191157.png]]