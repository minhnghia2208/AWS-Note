# Amazon Elastic Kubernetes Service
- Managed Kubernetes clusters on AWS
- Alternative to ECS
- EKS supports EC2 and Fargate

## EKS - Node Types
- Managed Node Groups:
    - Auto creates and manages Nodes (EC2 instances)
    - Nodes are part of ASG managed by EKS
    - Support On-Demand or Spot Instances

- Self-Managed Nodes
    - Nodes created by user and registered to EKS cluster and managed by ASG
    - User can use prebuilt AMI - Amazon EKS Optimized AMI
    - Supports On-Demand or Spot Instances
- AWS Fargate
    - No maintenance required, no nodes managed

## EKS - Data Volumes
- Leverage **Container Storage Interface (CSI)** compliant driver
- Support EBS, EFS, FSx for Lustre, FSx for NetApp ONTAP