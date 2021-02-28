
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
  * EC2 *
  * Elastic Bean Stalk *
  * Lambda *
  * But Elastic Container Service * or Elastic Kubernetes Service is not stressed on the exam
* Storage
  * S3 (1st service ever launched by AWS) *
  * EBS *
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

https://aws.amazon.com/s3/


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

https://aws.amazon.com/glacier/

A specialized version of S3 for cold storage (archiving data)


### EBS - Elastic Block Storage

https://aws.amazon.com/ebs/

Per-operation latency: Lowest, consistent
Throughput: Single GB/s
Access: Single EC2 in a single AZ

Use cases: boot volumes, transactional and no-sql databases, data warehousing & ETL

### EFS - Elastic File Storage

https://aws.amazon.com/efs/

Simple, scalable, fully managed elastic NFS file system 
Shareable hierarchical file system
Can't be shared with Windows VM
Stored redundantly across multiple AZs
Uses a traditional file permissions model, file locking capabilities, and hierarchical directory structure via the NFSv4 protocol
With Private Link it's possible to create a service to access your EFS as an endpoint (Elastic Network Interface) within your VPC.

Per-operation latency: Low, consistent
Throughput: Multiple GB/s
Access: 1-1000s of VMs instances (VMs or on-premise) from multiple AZs concurrently.

Use cases: web serving, CMS, enterprise apps, media and entertainment, home directories, database backups, developer tools, container storage, big data analytics

### Amazon FSx

AWS FSx is an AWS-managed service for popular file systems
Intended to be cost-optimized b/c the networked attached storage (NAS) hardware is not demanding. 

Two types offered:
* [Amazon FSx for Lustre](https://aws.amazon.com/fsx/lustre/) for compute-intensive workloads.
* [Amazon FSx for Windows File Server](https://aws.amazon.com/fsx/windows/) for business applications
  * Can be secured by AWS-managed Active Directory or self-managed Active Directory.
  * Intent is to simplify set up of the compute instances that run the FSx so that the AWS set up is more declarative.


### AWS Storage Gateway

https://aws.amazon.com/storagegateway/

A software appliance that connects your on-premise storage on your local on-premise network to AWS cloud. Can use:

1. File-based (NFSv4) 
2. Volume-based (internet SCSI)
3. Tape-based

You can choose to install a VM on your network or setup an EC2 instance

File Gateway provides an interface to S3 buckets.

### Storage Access Security

From AWS CLI, `aws s3api` is the set of APIs that can manage S3 buckets: will include setting the security policy.

Be aware of 2 metrics of measuring size: one is decimal-based preferred by networking folks, but the other is binary-based, preferred by storage folks.

Kilobyte - kB (1000)  -> Kibibyte - kiB (2^10 = 1024)
Megabyte - MB (10^6)  -> Mebibyte - MiB (2^20 = 1,048,576)
Gigabyte - GB (10^9)  -> Gibibyte - GiB (2^30 = 1,073,741,824)
Terabyte - TB (10^12) -> Tebibyte - TiB (2^40 = 1,099,511,627,776)


## Virtual Private Cloud

[Virtual Private Cloud](https://aws.amazon.com/vpc/)

Definining Virtual Private Cloud
  - It makes a public code (e.g. AWS) act "as if" it were private cloud
  - It is a logical construct. VPC endpoints connect to AWS resources. The VPC endpoint can be controlled by policies.
  - VPN Connections can be made to the VPC
  - Applications can run in the VPC or on-premises
  - Subnets can be created within the VPC

Multiple VPCs can be interconnected using peering.
Distinguish between old use of an endpoint (any way to access a server throug a network) with AWS defining an endpoint as a channel secured by a policy to access an AWS resource.

All AWS accounts have a default VPC. One in each region. AMZ recoomends do not delete.

Features of VPC
  - Dynamic private IP
  - Dynamic public IP
  - AWS-provisioned DNS names - not human friendly
  - Private DNS names
  - Public DNS names

### Amazon VPC Applications

[AWS Direct Connect](https://docs.aws.amazon.com/directconnect/latest/UserGuide/Welcome.html)

- [Virtual Private Clouds](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)
  - [Your VPCs and Subnets](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Subnets.html)
    - Create a VPC -> VPCs do not talk to one another unless routes are built between them.
    - Classless Inter-Domain Routing (CIDR) - creates a private IPv4
    - Create a Subnet -> dedicates a set of the IPs that belong within a VPC

- Configuring DHCP Options
  - On premise, DHCP is setup by assigning ranges of IP addresses. AWS will have already done this when you defined a subnet.
  - So you need to [define a DHCP option for a subnet](https://console.aws.amazon.com/vpc/home?region=us-east-1#dhcpOptions:). A DHCP option is a configuration parameter related to an IP address protocol, the protocol we use to get an IP addresses in all the rest of our configuration on the device that receives the configuration set, so that it could be a client. It could be a server
  - Can define a DHCP option set name (recommended), domain name, domain name servers, network time protocol (NTP) servers, NetBIOS name servers and NetBIOS node types. NetBIOS is not frequently used today.

- Elastic IP addresses (EIPs)

EIP is a public IP address from the VPC and is allocated to an AWS region until it is released.
You are charged for it.
Network interfaces consume EIPs
EIPs can be moved between instances in the same region.
A way to ensure an EIP is not used (so that you can release it and not pay for it) is to check that there is no instance associated with it.

- Endpoints


### VPC Peering

### Amazon VPC Security

### VPC Resources

All VPC Resources are the building blocks to build a network in the cloud

#### [Virtual Private Clouds](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)

- [Route Tables](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Route_Tables.html)
- [Internet Gateways](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html)
- [Egress Only Internet Gateways](https://docs.aws.amazon.com/vpc/latest/userguide/egress-only-internet-gateway.html)
- [Carrier Gateways](https://docs.aws.amazon.com/vpc/latest/userguide/Carrier_Gateway.html)
- [DHCP Options Set](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_DHCP_Options.html)
- [Elastic IPs](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-eips.html)
- [Managed Prefix Lists](https://docs.aws.amazon.com/vpc/latest/userguide/managed-prefix-lists.html)
- [Endpoints](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints.html) appears to be part of AWS PrivateLink
- [Endpoint Services](https://docs.aws.amazon.com/vpc/latest/privatelink/endpoint-service.html) appears to be part of AWS Private Link
- [NAT Gatweways](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html)
- Peering Connections

#### [Security](https://docs.aws.amazon.com/vpc/latest/userguide/security.html)

- [Network ACLs](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html)
- [Security Groups](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html)

#### Reachability

- [Reachability Analyzer](https://docs.aws.amazon.com/vpc/latest/reachability/what-is-reachability-analyzer.html)


#### [AWS Network Firewall](https://docs.aws.amazon.com/network-firewall/)

- Firewalls
- Firewall policies
- Network Firewall rule groups


#### Virtual Private Network (VPN)

- Customer gateways
- Virtual Private Gateways
- Site-to-Site VPN Connecitons
- Client VPN Endpoints

#### [Transit Gateways](https://docs.aws.amazon.com/vpc/latest/tgw/what-is-transit-gateway.html)

- Transit Gateways
- Transit Gateway Attachments
- Transit Gateway Route Tables
- Transit Gateway Multicast
- Network Manager


#### [Traffic Monitoring](https://docs.aws.amazon.com/vpc/latest/mirroring/what-is-traffic-mirroring.html)

- Mirror Sessions
- Mirror Targets
- Mirror Filters


## Compute Services

[Compute Services](https://aws.amazon.com/products/compute/)

## Identity and Access Management

[Identity and Access Mangement](https://aws.amazon.com/iam/)

## Auto Scaling and Virtual Network Services

[Auto Scaling](https://aws.amazon.com/autoscaling/) and Virtual Network Services

## Application Development

Application Development

[Developer Tools](https://aws.amazon.com/products/developer-tools/)

## Databases

[Databases](https://aws.amazon.com/products/databases/)

## Services and Design Scenarios

Services and Design Scenarios
