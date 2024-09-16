# Kinesis Overview
- **Collecting**, **processing**, and **analyzing** streaming data in real-time
- Ingest real-time data such as: Application logs, metrics, website clickstreams, IoT
- **Kinesis Data Streams**: Capture, process, and store data streams
- **Kinesis Data Firehose**: Load data Streams into AWS data stores
- **Kinesis Data Analytics**: analyze data streams with SQL or Apache Flink
- **Kinesis Video Streams**: capture, process, and store video streams

## Kinesis Data Streams
- Retention between 1 - 365 days
- Ability to reprocess data
- Once data is inserted in Kinesis, it can't be deleted (immutability)
- Data that shares the same partition goes to the same shard (ordering)
- **Producers**: AWS SDK, Kinesis Producer Library (KPL), Kinesis Agent
- **Consumers**:
    - Write your own: Kinesis Client Library (KCL), AWS SDK
    - Managed: AWS Lambda, Kinesis Data Firehose, Kinesis Data Analytics

### Capacity modes:
    - Provisioned mode:
        - Choose number of shards provisioned, scale manually
        - Each shard gets 1 MB/s in (or 1000 records per second)
        - Each shard gets 2 MB/s out (classic or enhanced fan-out consumer)
        - You pay per shard provisioned per hour
    - On-demand mode:
        - Capacity is auto managed
        - Default capacity provisioned (4 MB/s in or 4000 records per second)
        - Scales automatically based on observed throughput peak during the last 30 days
        - Pay per stream per hour & data in/out per GB

### Security
- Control authentication / authorization using IAM policies
- Encryption in flight using HTTPS
- Encryption at rest using KMS
- Client side Encryption/Decryption
- VPC endpoints

## Kinesis Data Firehose
- Fully managed service, no administration, automatic scaling, serverless
- Pay for data going through Firehose
- Near real time:
    - Buffer interval: 0 - 900 sec
    - Buffer size: minimum 1 MB

## Amazon MQ
- Is a managed message broker service for RabbitMQ, ActiveMQ
- Not as scale as SQS and SNS