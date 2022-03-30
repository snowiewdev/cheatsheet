# AWS Cloud Practitioner Notes

## Client-server Model
- client: web browser/desktop application that make requests to computer server
- server: can be Amazon EC2, like virtual server

## Cloud Computing
- On-demand delivery of IT resources and applications through the internet with pay-as-you-go pricing
- the cloud usage from large number of customers results in lower pay-as-you-go prices, thus saving cost

### Advantages
- services on demand
- pay only for what you use (variable expense)
- cost optimization (maintainence/ run data center handled by AWS)
- can scale in & out as needed, no need to guess capacity
- increase speed & agility, quickly deployed worldwide
- able to use aws global infrastructure

### Cloud computing deployment models
- Cloud-based deployment: run, migrate, design & build application in the cloud
- On-premises deployment: private cloud deployment, deploy resources by using virtualization & resource management tools
- Hybrid deployment: connect cloud-based resources to on-premises infrastructure, like legacy IT applications


## Amazon EC2
- use secure, resizable compute capacity in cloud as EC2 instance (virtual server)
- boot/launch server instance in minutes
- pay only for what you use, the compute time when an instance is running

### Instance type
- General Purpose: balance compute, memory & networking resource
- Compute Optimized: High performance processing (CPU), like gaming server and batch-processing
- Memory Optimized: for high-performance database
- Accelerated Computing: uses hardware accelerators, for handling streaming & graphic workload
- Storage Optimized: for workloads require high, sequential read & write access to large dataset, data warehouse
- Input/Output Operations Per Second (IOPS)

### Pricing Options
- On-Demand: for short-term, irregular worklaod that cannot be interrupted(first time)
- Spot Instance: can withstand interruption, for testing or short-term use with flexible start & end times
- Savings Plan: have discount package over on-demannd pricing (1 or 3 year term)
- Dedicated Instance/ Reserved Instance: biling discount with (1 or 3 year term)
- Dedicated Server: physical server with EC2 fully dedicated for your use

### Auto-Scaling
- scale capacity (add/remove EC2 instance) as computing requirement/application demand change
- Dynamic Scaling: responds to changing demand
- Predictive Scaling: schedule right number of EC2 instance based on predicted demand
- Auto-Scaling group: Minimum instance, desired instance, scale as needed instance/ maximum capacity

### Elastic Loading-Balancing (ELB)
- automatically distribute application traffic across resources, like EC2
- Need ELB for auto-scaling to apply

### Communication between server
- Monolithic Application: an application with tightly coupled componetns, if a single component fail, other fails too, so as the application
- Microservices Approach: application components are loosely coupled, prevents entire application from failing when one fails
- Amazon Simple Notification Service (Amazon SNS): a publish/ subscription serivce
- Amazon Simple Queue Service (Amazon SQS): message queuing service

### AWS Lambda 
- Serverless computing service
- run code without managing server, only pay for compute time while code is running, flexible to scale serverless app automatically
- upload code to Lambda, set code to trigger from an event source, code runs only when triggered, pay only for compute time you used

### AWS Elastic Container Service (ECS)
- container: standard way to package application code & dependencies into a single object
- container enables us to build, test & deploy application quickly
- container management system that allows you to run & scale containerized application, like Docker container

### AWS Elastic Kubernetes Service (EKS)
- container management system that allows you to run & scale Kubernetes application

### AWS Fargate
- Run serverless containers with Amazon ECS / Amazon EKS
- no need to provide/manage server


## AWS Global Infrastructure
- select region based on: Proximity to customer, Available Services in region, Pricing, Compliance with data governance & legal requirement
- a Region contains 2 or more Availablity Zones (AZ) (AZ = 1 or more Data Center)

### Amazon CloudFront
- Content Delivery Network (CDN) to deliver caching static files in Edge Location (~3xx)
- Edge Location: site used to store cached copies of content for faster delivery
- improve site speed & reducing loading workload on original server
- 1TB free traffic

### AWS Outposts
- extend AWS infrastructure & service to your on-premise (private) data center

## Ways to accessing and managing AWS services
### AWS management console  
- web-based interface for accessing and managing AWS services 
- includes wizards and automated workflows that can simplify the process of completing tasks

### AWS command line interface (CLI)
- enables you to control multiple AWS services directly from the command line within one tool

### Software development kits (SDKs)
- allow you to use AWS services through an API designed for your programming language or platform


## Networking
### Amazon Virtual Private Cloud (VPC)
- allow you to launch resources in a virtual network that you define
- Internet Gateway: a component used to connect VPC to the Internet, applow public traffice from Internet to access your VPC
- Virtual Private Gateway: a component that allows protected internet traffic to enter into the VPC
- AWS Direct Connect: dedicated private connection between on-premise data center & the VPC

- Subnet: a section of VPC that you define to control access of group resources
- In a VPC, subnets can communicate with each other
- Public Subnet (EC2 instance): provide Internet Gateway & allow public user to access
- Private Subnet (database): provide virtual private gateway via virtual private network(VPN) connection for limited user to access, used to isolate db


Network Traffic: A packet is a unit of data sent over the internet or a network

Client Packet -> Internet Gateway -> Network ACL -> Security group -> public subnet

### Security Group
- virtual firewall that controls inbound and outbound traffic for an Amazon EC2 instance
- default denies all inbound traffic, allows all outbound traffic
- stateful packet filtering (check in-connection only), remember previous decision made for incoming packets

### Network Access Control List (ACL)
- virtual firewall that control inbound & outbound traffic at subnet level
- default allow all access/ traffic 
- stateless packet filtering (check in-connection & out-connection)

### Domain Name System
- convert domain name to IP address via DNS resolver
- Amazon Route 53 (DNS), use port 53 so it is how it named, allow purchase of domain name

## Storage
- instance store: provides temporary block-level storage for EC2 instnace, a disk storage physically attached to host computer
- Amazon Elastic Block Storage (EBS) for long term data storage, allow data retention even there's termination of EC2

### Block storage 
- = Hard disk
- Instance store: store data only when running, once instance is turned off, data will be gone, like RAM
- Elastic Block store: store things permanently
- EBS snapshot: incremental backup of data, first backup = full backup, subsequent backup: only data that has changed recently is backed up

### Object Storage
- each object consist of Data, Metadata, Key
- store object in buckets
- set permission to control access to object
- AWS Simple Storage Service (S3), 3 copies

### Storage Class for Object Storage
- S3 Standard: for frequently accessed data, store data in minimum of 3 AZ
- S3 Standard-IA: infrequent-access, store data in minimum of 3 AZ
- S3 One-Zone IA: cheaper, stores data in a single AZ
- S3 Intelligent-Tiering*: for data storage with unknown access pattern, will dynamically switch to S3 Stanard or S3 Standard-IA depends on the access pattern
- S3 Glacier/ S3 Glacier Deep Archive - for archival data, for data not frequently used 
- Glacier (retrieve object within minutes-hours), Glacier Deep Archive (retrieve object within 12 hours)

### File Storage
- clients can access data that is stored in shared file folders
- AWS Elastic File System (EFS): store data in scalable file system
- EBS volume store data in Single Availabilty Zone, EFS store data across Multiple Availability Zone (Regional Service)

## Database
### Relational Database
- use Structured Query Language SQL to store/ query/ organize data
- AWS Relational Database Service (RDS): setup, patching & backup of database
- offers data encryption when stored & encryption in transit
- RDS database engines: PostgreSQL, MySQL, MariaDB, Amazon Aurora (support MySQL & PostgreSQL), Oracle DB, Microsoft SQL Server
- Amazon Aurora: replicates six copies of your data across three Availability Zones and continuously backs up your data to Amazon S3

### Non-relational Database
- use structure other than rows & columns to organize data
- data organized into key-value pairs
- Amazon DynamoDB: serverless key-value database, auto-scaling available

### AWS Database Migration Service (DMS)
- migrate data stores, allow schema convertion like from MySQL to Aurora

### Additional Database Service
- Amazon Redshift: data warehousing service for big data analytics
- Amazon DocumentDB: run & support MongoDB
- Amazon Neptune: graph database service, for highly connected datasets
- Amazon QLDB: review complete history of changes in database
- Amazon Managed Blockchain: decentralized database
- Amazon ElastiCache: add caching layer to db to improve read times of request, like Redis & Memcached
- Amazon DynamoDB Accelerator: improve DynamoDB response time via in-memory cache

## Security
- shared responsibility model between AWS & customer
- AWS: network infrastructure, edge
- customer: patching software, HTTP to HTTPS

### IAM
- root user: only one, create first IAM user & give permission to other user
- IAM user
- IAM Policy: a document that control access permission (grant/denies) of users
- IAM group: collection of IAM users, & attach IAM policy to that group for easier management
- IAM role: assume role & permission

### Multi-factor authenication (MFA)
- provide extra layer of protection of your account

### AWS Artifact
- provide access to security & compliance report, online agreements with AWS
- Customer Compliance Center: provide resources for compliance 

### AWS Web Application Firewall (WAF)
- handle malicious request from hacker

### AWS Shield
- provide protection against DDoS attacks, default contains basic shield
- DoS (Denial of service attack)
- DDoS (Distributed Denial of service attack)

### AWS inspector
- provide assessment on EC2

### AWS Key Managment Service (KMS)
- used to encrypt & descrypt data, create cryptographic keys (public & private keys)

### Amazon GuardDuty
- provide intelligent threat detection 

## Monitoring & Analytics
### Amazon CloudWatch
- dashboard that allow you to monitor & access metrics/performance of your infrastructure & application
- allow you to set alert when needed

### Amazon CloudTrail
- track user activities and API requests (what, who, when, how)
- filter logs to assist with operational analysis & troubleshooting

### AWS Trusted Advisor
- provide real-time guidance for improving AWS environment
- guidance/checking on 5 areas, i.e. cost optimization, performance, security, fault torlerance, service limit

## Pricing & Support
- pay as you go, only charge on data transferring out
- AWS Pricing Calculator: cost estimation
- AWS Budgets: tool that allow you set thresholds for service usage & costs
- AWS Cost Explorer: tool allow you to visualize & manage your AWS application cost
- Basic Support: free tier support but limited
- Developer Support: practice guidiance
- Business Support: includes all AWS Trusted Advisor Checks
- Enterprise Support: has Technical Account Manager (TAM) support
- AWS Marketplace: provide listing of third-party software that runs on AWS, e.g. data analytics
- Consolidated billing: combine usage across amount to get discount

## Migration
- 6 areas to consider for cloud migration to AWS
- Business perspective: business, people (staffs), governance
- Technical perspective: platform, security, operations (minimize workload?)
- Six Migration Stratgies to identify whether migration is needed: rehost, replatform, reafactor/rearchitect, repurchase (need migration) || retain, retire (No need migration)

### AWS Snow Family
- Physical Device that helps you to transfer data/ migration
- AWS Snowcone: 8TB of storage
- AWS Snowball device: 1PB of storage (1000TB = 1PB)
- AWS Snowmobile: transfer up to 100PB of Data

### Well-Architect Framework
- Operational Excellence: run & monitor system
- Security: protect information & assets, permission
- Reliability: recovery procedure, stability, able to scale
- Performance efficiency
- Cost Optimization

### Exam notes
- max score 1000, 700 passing score
- 90 mins, all MCQs (~60), +/- 30 min extension (ESL +30 mins)
- Certification -> Exam Registration
