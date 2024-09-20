# Amazon Elastic Container Service (ECS)
## EC2 Launch Type
- User must provision and maintain the infrastructure (EC2 instances)
- Each EC2 instance must run the ECS Agent to register in the ECS Cluster
## Fargate Launch Type
- User doesn't need to provision infrastructure (No EC2 instances to manage)
- Create task definition
- AWS will spin up anything based on CPU/RAM need
## IAM roles for ECS
- TODO: Rewatch chap 18, 201
## Load Balancer Integrations
- **Application Load Balancer** supported and works for most use cases
- **Network Load Balancer** recommended only for high throughput / high performance use cases, or to pair with AWS Private Link
- **Clasic Load Balancer** Not recommended (not compatible with Fargate)
## Data Volumes (EFS)
- Mount EFS file system onto ECS tasks
- Works for both EC2 and Fargate

## ECS Service Auto Scaling
- Auto increase/decrease the desired number of ECS tasks
- ECS Auto Scaling uses AWS Application Auto Scaling
- **Target Tracking**: scale based on target value for a specific CloudWatch metric
- **Step Scaling**: scale based on a specified CloudWatch Alarm
- **Scheduled Scaling**: scale based on a specified date/time (predictable changes)
- ECS Service Auto Scaling (task level)
- EC2 Auto Scaling (EC2 instance level)

## EC2 Launch Type - Auto scaling EC2 Instances
- Auto Scaling Group Scaling
    - Scale ASG based on CPU utilization
    - Add EC2 instances over time
- ECS Cluster Capacity Provider
    - Adding Tasks to EC2 instances until EC2 resource run out
    - Add more EC2 instances when resource run out


