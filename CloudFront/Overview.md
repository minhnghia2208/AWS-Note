# AWS CloudFront
- Is a Content Delivery Network (CDN)
- Prevent DDoS attack

## ALB or EC2 as an origin
- Must allow Public IP of Edge locations

## Pricing
- More data transfer -> less price pay per data transfer
- Three Prices Class:
    1. Price Class All: Allow all edge regions
    2. Price Class 200: Allow most regions except most expensive regions
    3. Price Class 100: Allow least expensive regions

## Cache Invalidations
- You can force entire/partial cache fresh by performing **CloudFront Invalidation**
- You can invalidate all files (*) or a special path (/images/*)

## AWS Global Accelerator
- **Unicast IP**: one server holds one IP address
- **Anycast IP**: all servers hold the same IP address and the client is routed to the nearest one
- Use Anycast IP to send request to nearest Edge location. Data then be sent to host server via AWS internal server
- This process has better latency compare to sending request globally via public internet.
- Work with **EC2, Elastic IP, ELB**