- Highly secure offline portable devices
	- ==Data migration== into and out of AWS
	- ==Edge computing== - collect and process data at the edge
- Snow cone, Snow Ball Edge and Snow Mobile (for migration only)

## Data migration
- There can be challenges sometimes to transfer data over the network. 
- Thumb Rule: takes more than a week to transfer, then use snowball devices.

## Devices
1.  [[AWS Snowball Edge]] 
2. [[AWS Snowcone]]
3. [[AWS Snowmobile]]  

![[Pasted image 20240126000705.png]]

## Usage
1. Request a device 
2. ==install snowball client / [[AWS OpsHub]]== on your servers. 
3. connect the snowball and copy files using client. 
4. ship the device back 
5. data will be loaded on S3 bucket 
6. device is wiped.

## Edge Computing 
- Process data very close to the source where limited or no internet connectivity 
- Use: 
	- Preprocess data
	- machine learning at the edge 
	- transcoding media streams
- ==Use Snowball Edge or SnowCone==
- Eventually, ship back to AWS for transferring data

## Options
1. Snowcone & SnowCone SSD (smaller)
	1. 2 CPUs, 4GB of memory, wired or wireless access
	2. USB-C power using a cord or optional battery 
2. ==Snowball Edge - Compute Optimized== 
	1. 104 vCPUs, 416Gib of RAM
	2. optional GPU
	3. 28TB NVMe or 42TB HDD usable storage 
	4. Storage clustering available (upto 16 nodes)
3. Snowball Edge - storage optimized 
	1. up to 40 vCPUs, 80GB RAM, 80TB storage
4. All can run EC2 instances or lambda functions (using AWS IoT greengrass)
5. Long term discounts 1 to 3 years


## Snowball into Glacier
Must use S3 first in combination with an S3 lifecycle polciy,