
# LinkedIn Learning Path

[Prepare for the AWS Certified Solutions Architect - Associate Exam (SAA-C02)](https://www.linkedin.com/learning/paths/prepare-for-the-aws-certified-solutions-architect-associate-exam-saa-c02)

## Exam Tips

[Exam Tips](https://www.linkedin.com/learning/exam-tips-aws-certified-solutions-architect-associate-saa-c02/aws-solutions-architect?contextUrn=urn%3Ali%3AlyndaLearningPath)



Why the exam?
* 80% of companies are using AWS
* It proves that you know AWS

Why AWS?

* It’s the market leader.
  * 34% of market share in 2018q4.
  * Azure 15%
  * Google & IBM had 7%
* Big customers: Netflix, Pinterest, Instacart, Grab, etc.
* Massive catalog of services
  * 180 services in 20 service-categories
  * 69 AZs in 22 regions
* Extremely well-documented

Why the cloud?

* Little to no upfront investment
* Easy to provision a capability such as storage, compute or DB
* Pay for what you use, not 

Well-architected framework

* Resilient (30% of exam)
* Performant (28% of exam)
* Secure (24% of exam)
* Cost-optimized (18% of exam)
* Operationally excellent is spread throughout the exam

AWS Certifications

* 3 levels
  * Foundational (official: 6 months of experience)
  * Associate (official: 1 year of experience
  * Professional (official: 2 year of experience)
* 3 tracks:
  * Architect
    * Should focus on what capabilities there are, and what is the right one for a use case
  * Developer
  * Operations
* Specialty areas
  * Advanced networking
  * Security
  * Machine learning

Exam

* Should plan on scheduling it so that it motivates you to study
* Need a score of 720/1000

Exam objectives

* Resilient
  * Design a multi-tier architecture solution
  * Design a highly available and/or fault tolerant solution
  * Design decoupling mechanisms
  * Choose appropriate storage types
* Performant
  * Elastic and scalable compute 
  * High performing and scalable storage (EBS/EFS)
  * High-performing networking
  * RDS
* Secure
  * IAM 
  * Secure Application tiers
  * Secure data 
* Cost Optimized
  * Cost-effective storage
  * Cost-effective compute and databases
  * Cost-effective network

4 key areas

* Storage
* Compute
* Networking
* Databases

## Cloud Services Overview

[Cloud Services Overview](https://www.linkedin.com/learning/aws-certified-solutions-architect-associate-saa-c02-1-cloud-services-overview/aws-services-part-1?contextUrn=urn%3Ali%3AlyndaLearningPath%3A5f0f83ce498e4916ed6c9b22)

AWS Services

* Compute
  * EC2*
  * Elastic Bean Stalk*
  * Lambda*
  * But Elastic Container Service* or Elastic Kubernetes Service is not stressed on the exam
* Storage
  * S3 (1st service ever launched by AWS) *
  * EFS *
  * Glacier *
  * Storage Gateway
* Databases
  * RDS *
  * Dynamo *
  * ElastiCache
  * Neptune
  * Redshift *
* Migration
  * AWS Migration Hub
  * Application Migration Service
  * Database Migration Service
  * Server Migration Service
  * Snowball (AWS ships you a server for you to upload and they pick it up to upload at their data center :D)
* Networking & Content Delivery
  * VPC
  * CloudFront *
  * Route 53
  * API Gateway
  * Direct Connect
* Development Tools
* Management Tools
  * Cloud Watch
  * Autoscaling *
  * Cloud Formation
  * Cloud Trail
  * Ops Work
  * Trusted Advisor
* Media Services
* Machine Learning
* Analytics
  * Kinesis *
  * Athena
* Security, IAM & Compliance
  * IAM *
  * Cognito *
  * Secrets Manager
  * Guard Duty
  * Inspector *
  * Amazon Macie
  * AWS Organizations *
  * AWS Single Sign On
  * Certificate Manager
  * Cloud HSM *
  * Directory Services *
  * WAF & Shield *
  * Artifact
* Cost Management
* Mobile Services
* AR & VR
* Application Integration
  * Simple Notification Service *
  * Simple Queue Service *
* Customer Engagement
* Business Productivity
* Desktop & App Streaming
* Internet of Things (IoT)
* Game Development

Security and Compliance

* Compliance
  * PCIDSS (payment card industry data security standard)
  * HIPAA
* Shared Responsibility Model
  * AWS is responsible for (foundational) security of the cloud
    * E.g. Physical security of the data center
  * Customer is responsible for security in the cloud
    * Their customer data
    * Their own instances they’ve set up on AWS. e.g. since customers set up the OS for any AMI of an EC2 VM, security patches of the OS are the customer's responsibility

Regions and Availability Zones

* Regions are a geographical area that will have multiple data centers
  * E.g. US East
  * Regions have multiple AZs
* AZs
  * Have 1-6 data centers
  * Has redundant power and networks
* Edge Areas


## Storage Design

[Storage Design](https://www.linkedin.com/learning/aws-certified-solutions-architect-associate-saa-c02-2-storage-design/storage-services?contextUrn=urn%3Ali%3AlyndaLearningPath%3A5f0f83ce498e4916ed6c9b22)

### S3 - Simple Storage Service

S3 Storage Classes?

S3 terminology

S3 bucket properties?


S3 is a highly distributed object store - not really hierarchical (uses "tags")
(low latency) - akin to Hadoop HDFS

Per-operation latency: Low, for mixed request tests, and integrated with Cloud Front CDN
Throughput: Multiple GB/s
Access: 1 to millions of connections over the web.

Use cases: web serving, CMS, media and entertainment, backups, bit data analytics, data lake.

#### Amazon Glacier

A specialized version of S3 for cold storage (archiving data)

#### AWS Storage Gateway


### EFS - Elastic File Storage

Shareable hierarchical file system
Can't be shared with Windows VM
Stored redundantly across multiple AZs

Per-operation latency: Low, consistent
Throughput: Multiple GB/s
Access: 1-1000s of VMs instances (VMs or on-premise) from multiple AZs concurrently.

Use cases: web serving, CMS, enterprise apps, media and entertainment, home directories, database backups, developer tools, container storage, big data analytics

### EBS - Elastic Block Storage

Per-operation latency: Lowest, consistent
Throughput: Single GB/s
Access: Single EC2 in a single AZ

Use cases: boot volumes, transactional and no-sql databases, data warehousing & ETL

### Amazon FSx


## Virtual Private Cloud

Virtual Private Cloud

## Compute Services

Compute Services

## Identity and Access Management

Identity and Access Mangement

## Auto Scaling and Virtual Network Services

Auto Scaling and Virtual Network Services

## Application Development

Application Development

## Databases

Databases

## Services and Design Scenarios

Services and Design Scenarios
