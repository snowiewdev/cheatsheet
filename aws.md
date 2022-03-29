## Cloud Computing
### Advantages
- services on demand
- pay only for what you use (variable expense)
- cost optimization (maintainence/ run data center handled by AWS)
- can scale in & out as needed, no need to guess capacity
- speed & agility, quickly deployed worldwide
- able to use aws globle infrastructure

### Cloud computing deployment models
- Cloud, on premises, hybrid

## Amazon EC2
- use secure, sizable compute capacity
- boot server instance in minutes
- pay only for what you use

### Instance type
- General Purpose: balance compute, memory & networking resource
- Compute Optimize: High performance processing (CPU)
- Memory Optimized: for high-performance database
- Accelerated Computing: streaming & graphic workload
- Storage Optimized

### Pricing Options
- On-Demand: for short-term, irregular worklaod (first time)
- Spot
- Reserved: have discount over on-demannd pricing (1 or 3 year)

- Dedicated instance
- Dedicated server

### Auto-Scaling
- scale capacity as computing requirement change
- Minimum instance, desired instance, scale as needed instance (auto-scaling group)

### Elastic Loading-Balancing (ELB)
- distribute traffic across resources

## Communication between server
- Amazon Simple Notification Service (Amazon SNS)
- Amazon Simple Queue Service (Amazon SQS)

## AWS Lambda 
- Serverless computing service
- run code without managing server, only pay for compute time while code is running
- upload code to Lambda, set code to trigger from an event source, code runs only when triggered, pay only for compute time you used

## AWS Elastic Container Service (ECS)
- run & scale containerized application

## AWS Elastic Kubernetes Service (EKS)
- run & scale Kubernetes application

## AWS Fargate
- Run serverless containers with Amazon ECS / Amazon EKS
