
# Storage Design

[Storage Design](https://www.linkedin.com/learning/aws-certified-solutions-architect-associate-saa-c02-2-storage-design/storage-services?contextUrn=urn%3Ali%3AlyndaLearningPath%3A5f0f83ce498e4916ed6c9b22)

## S3 - Simple Storage Service

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

### Amazon Glacier

https://aws.amazon.com/glacier/

A specialized version of S3 for cold storage (archiving data)


## EBS - Elastic Block Storage

https://aws.amazon.com/ebs/

Per-operation latency: Lowest, consistent
Throughput: Single GB/s
Access: Single EC2 in a single AZ

Use cases: boot volumes, transactional and no-sql databases, data warehousing & ETL

## EFS - Elastic File Storage

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

## Amazon FSx

AWS FSx is an AWS-managed service for popular file systems
Intended to be cost-optimized b/c the networked attached storage (NAS) hardware is not demanding. 

Two types offered:
* [Amazon FSx for Lustre](https://aws.amazon.com/fsx/lustre/) for compute-intensive workloads.
* [Amazon FSx for Windows File Server](https://aws.amazon.com/fsx/windows/) for business applications
  * Can be secured by AWS-managed Active Directory or self-managed Active Directory.
  * Intent is to simplify set up of the compute instances that run the FSx so that the AWS set up is more declarative.


## AWS Storage Gateway

https://aws.amazon.com/storagegateway/

A software appliance that connects your on-premise storage on your local on-premise network to AWS cloud. Can use:

1. File-based (NFSv4) 
2. Volume-based (internet SCSI)
3. Tape-based

You can choose to install a VM on your network or setup an EC2 instance

File Gateway provides an interface to S3 buckets.

## Storage Access Security

From AWS CLI, `aws s3api` is the set of APIs that can manage S3 buckets: will include setting the security policy.

Be aware of 2 metrics of measuring size: one is decimal-based preferred by networking folks, but the other is binary-based, preferred by storage folks.

Kilobyte - kB (1000)  -> Kibibyte - kiB (2^10 = 1024)
Megabyte - MB (10^6)  -> Mebibyte - MiB (2^20 = 1,048,576)
Gigabyte - GB (10^9)  -> Gibibyte - GiB (2^30 = 1,073,741,824)
Terabyte - TB (10^12) -> Tebibyte - TiB (2^40 = 1,099,511,627,776)

