### AWS Snow Family
- Secure and Portable storage devices
- If transfering data take more than 1 week, use Snow device
- 2 types of snow devices:
    1. Snowcone: 8 TB HDD -> 14 TB SSD
    2. Snowball Edge: 80 TB -> 210 TB

### Transferring process:
- Devices are ordered and shipped to your location
- Install snow location / AWS OpsHub on your servers
- Upload data to snow devices from servers
- Ship devices back to AWS facility
- Data is uploaded to S3
- Data is then wiped

### Snowball into Glacier
- Snowball data cannot be uploaded to Glacier tier
- We have to upload data to S3 then use lifecycle policy to convert data to Glacier