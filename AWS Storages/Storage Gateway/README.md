### Storage Gateway
- Bridge between on-premises data and cloud data


### Amazon S3 File Gateway
- On-premises communicate with S3 File Gateway via NFS or SMB protocols
- S3 File Gateway communicate with S3 Bucket via HTTPS
- Most recently used data is cache in the file gateway
- Support for:
    1. S3 Standard
    2. S3 Standard IA
    3. S3 OneZone IA
    4. S3 Intelligent Tiering

### Amazon FSx File Gateway
- Local cached for frequent accessed data

### Amazon Volume Gateway
- Cached volume
- Stored volume: entire data is on premise, schedule backup to S3

### Amazon Tape Gateway