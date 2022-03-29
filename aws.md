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

### Communication between server
- Amazon Simple Notification Service (Amazon SNS)
- Amazon Simple Queue Service (Amazon SQS)

### AWS Lambda 
- Serverless computing service
- run code without managing server, only pay for compute time while code is running
- upload code to Lambda, set code to trigger from an event source, code runs only when triggered, pay only for compute time you used

### AWS Elastic Container Service (ECS)
- run & scale containerized application

### AWS Elastic Kubernetes Service (EKS)
- run & scale Kubernetes application

### AWS Fargate
- Run serverless containers with Amazon ECS / Amazon EKS


## AWS Global Infrastructure
- select region based on proximity to customer, available services in region, pricing, compliance with data governance & legal requirement
- region contains 2 or more availablity zones (AZ) (data center)
- AWS management console, AWS CLI, SDKs

### Amazon CloudFront
- Content Delivery Network (CDN) to deliver caching static files in Edge Location (~3xx)
- improve site speed & reducing loading workload on original server
- 1TB free traffic in

### AWS Outposts
- extend AWS infrastructure & service 

## Networking
### Amazon Virtual Private Cloud (VPC)
- allow you to launch resources in a virtual network that you define
- subnet: region that you define to control access
- public subnet (EC2 instance), provide Internet Gateway & allow user to access
- private subnet (database), provide virtual private gateway via VPN connection for limited user to access
- AWS direct connect

Network Traffic: ACL -> security group -> public subnet

### Security Group
- default denies all inbound traffic
- stateful packet filtering (check in-connection only)

### Network Access Control List (ACL)
- default allow all access/ traffic 
- stateless packet filtering (check in-connection & out-connection)

### Domain Name System
- convert domain name to IP address via DNS resolver
- Amazon Route 53 (DNS), allow purchase of domain name

## Storage
### Block storage 
- = Hard disk
- Instance store: store data only when running, once instance is turned off, data will be gone, like RAM
- Elastic Block store: store things permanently
- EBS snapshot: back up of data, only data that has changed 

### Object Storage
- each object consist of Data, Metadata, Key
- store object in buckets
- set permission to control access to object
- AWS Simple Storage Service (S3)

### Storage Class for Object Storage
- S3 Standard: for frequently accessed data
- S3 Standard-IA: infrequent-access
- S3 One-Zone IA: cheaper
- S3 Intelligent-Tiering*: for data storage with unknown pattern, will dynamically 

### File Storage
- clients can access data that is stored in shared file folders
- AWS Elastic File System (EFS): store data in scalable file system

## Database
### Relational Database
- use SQL to organize data
- AWS Relational Database Service (RDS): backup of database
- RDS database engines: PostgreSQL, MySQL, MariaDB, Amazon Aurora (support MySQL & PostgreSQL)

### Non-relational Database
- use structure other than rows & columns
- data organized into key and values
- Amazon DynamoDB: serverless key-value database

### AWS Database Migration Service (DMS)
- migrate data stores, allow schema convertion like from MySQL to Aurora

### Additional Database Service
- Amazon Redshift: query & analyze data across a data warehouse
- Amazon DocumentDB: run MongoDB
- Amazon Neptune: highly connected datasets
- Amazon QLDB: review complete hostry of changes in database
- Amazon Managed Blockchain: decentralized database
- Amazon ElastiCache: caching layer
- Amazon DynamoDB Accelerator: improve DynamoDB response time
