# Amazon Simple Notification Service (SNS)
- Is a Pub/Sub service
- There are 2 roles publisher and subcriber
- Publisher sends messages to SNS topic
- Subcriber listen to SNS topic
- 100,000 topics limit
- Up to 12,500,000 subcriptions per topic

### How to publish
- Topic publish (using SDK)
    - Create a topic
    - Create subscriptions
    - Publish to the topic

- Direct Publish (for mobile apps SDK)
    - Create a platform application
    - Create a platform endpoint
    - Publish to the platform endpoint
    - Works with Google GCM, Amazon ADM, Apple APNS, ...

### Amazon SNS - Security
- Encryption:
    - In-flight encryption using HTTPS API
    - At rest encryption using KMS keys
    - Client-side encryption

### SNS + SQS: Fan out pattern
![alt text](./FanOut.png?raw=true "Title")
- Instead of having Buying Service send data to Service 1 and Service 2
- We publish event to SNS topic, this helps decoupling
- SQS helps: data persistence, delayed processing and retries of work

# SNS - Message Filtering
- JSON policy used to filter messages sent to SNS topic's subcriptions
- If subcription doesn't have filter policy, it receives every messages
