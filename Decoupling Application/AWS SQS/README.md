# AWS Simple Queues Service (SQS)
- Message Queue
- Fully managed service, used to decouple application
- Unlimited throughput, unlimited number of message in queue
- Default message retention: 4 days, 14 days max
- Low latency (<10ms) for publish and receive
- Maximum 256 Kb per message
- Can have duplicated message (at least one delivery)
- Can have out of order message (best effort ordering)

### SQS - Producing message
- Producer produces messages using SDK
- The message persistes in queue until consumer deletes it
- retention period: 4 - 14 days

### SQS - Consuming message
- Consumer polls/receives for messages (up to 10 messages at a time)
- Consumer has option to delete message after use (no other consumer can see it)

### SQS - Security
- In-flight encryption using HTTPS 
- At-rest encryption using KMS
- Client can encrypt on their side

### SQS - Message visibility timeout
- When message is received by a Consumer, other Consumers will not be able to see it
- Default invisible time is 30s, which mean no other Consumers see the message during 30s
- The message will be visible again after the set time, unless it is deleted by the Consumer
- If the Consumer needs more time to process the message, the Consumer can call **ChangeMessageVisibility API** to get more time

### SQS - Long Polling
- The Consumer has option to wait for message if there is none in the queue
- The wait period can be from 1 - 20 seconds
- Long Polling can be enable at Queue level or by calling **WaitTimePeriod API** at application level

### SQS - FIFO Queue
- Order is guaranteed
- Limited throughput: 300 msg/s without batching, 3000 msg/s with batching
- Exactly one send capability (by removing duplicate)
- Messages are processed by order

### SQS with ASG
- Use CloudWatch Metric to measure queue length, scale out if queue size increase and otherwise
- We can use SQS Queue in-between backend and DB to ensure transaction integrity
