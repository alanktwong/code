# Compute Services

[LinkedIn Learning Video Course: Compute Services](https://www.linkedin.com/learning/aws-certified-solutions-architect-associate-saa-c02-4-compute-services?contextUrn=urn%3Ali%3AlyndaLearningPath%3A5f0f83ce498e4916ed6c9b22)

[Compute Services CLP](https://aws.amazon.com/products/compute/)

## Compute Services Design

### EC2 Overview

[AWS EC2 Documentation](https://docs.aws.amazon.com/ec2/index.html)
2nd most important area of AWS after storage

Takes advantage of Elastic Block Storage

What is EC2?
* It's a virtual machine on a AWS cloud
* Pay as you go
* Integrates with storage, networking, security
* It's fast to provision
* Supports the following OS
    *  Windows 2003 R2 through 2016
    *  Amazon Linux
    *  Debian
    *  SUSE
    *  CentOS
    *  Red Hat Enterprise Linux
    *  Ubuntu

Advantages of ECS2
* Faster time to market
* Scalability
* Relability
* Securable
* Easier to operate/control
* Services integration (e.g. integrate to RDS)
* Cost effective

How to deploy EC2
1. Select an Amazon Machine Image (AMI) -> snapshot of a VM at a particular configuration state
2. Select networking/security
3. Choose instance type (e.g. low performance with low cost or high performance with high cost?)
4. Choose availability zone (AZ)
5. Attach elastic block storage (EBS)

### [EC2 Instance Types](https://aws.amazon.com/ec2/instance-types/)


Instance type determines compute power and cost of your EC2 VM

* General Purpose
    * T2, M5, M4, M3
        * T2 provides burst performance
            * Credits accrue during idle times
            * Credits used during burst operation
        * M3, M4 and M5 have no burst option
    * Balanced for networking and memory resources
    * Intended for something that is used consistently but not with heavy traffic.  General purpose instances provide a balance of compute, memory and networking resources, and can be used for a variety of diverse workloads. These instances are ideal for applications that use these resources in equal proportions such as web servers and code repositories. 
* Compute Optimized
    * C5, C4, C3
    * used for CPU-intensive applications
        * Media coding
        * Batch jobs
        * Scientific computing
        * Gaming servers
    * Compute Optimized instances are ideal for compute bound applications that benefit from high performance processors. Instances belonging to this family are well suited for batch processing workloads, media transcoding, high performance web servers, high performance computing (HPC), scientific modeling, dedicated gaming servers and ad server engines, machine learning inference and other compute intensive applications.
* Memory Optimized
    * R4, R3, X1e, X1
    * Memory optimized instances are designed to deliver fast performance for workloads that process large data sets in memory, in-memory data grids, Big Data processing (e.g. Spark)
    * Possible to get storage-optimized capability by connecting to better EBS
* Storage Optimized
    * H1, I3, D2
    * Useful for high sequential read/writes to local storage.
    * Storage optimized instances are designed for workloads that require high, sequential read and write access to very large data sets on local storage. They are optimized to deliver tens of thousands of low-latency, random I/O operations per second (IOPS) to applications.
        * RDBMS
        * Data Warehouses
        * Image storage/processing
* Accelerated Computing
    * P3, P2, G3 and F1
    * Accelerated computing instances use hardware accelerators, or co-processors, to perform functions, such as floating point number calculations, graphics processing, or data pattern matching, more efficiently than is possible in software running on CPUs.
        * FPGA
        * GPUs
* Instance Features
* Measuring Instance Performance


### EC2 Pricing

### EBS and EC2

## Compute Services Implementation

### Lab: Launching an EC2 Linux instance

### Lab: Configuring an EC2 Linux instance

### Lab: Setting up an EC2 Windows instance

### Shared tenancy

### Dedicated hosts

### Dedicated instances

### AMI virtualization

## Compute Services Management

### Instance management

### Lab: connecting to instances

### Working with security groups

### Lab: Working with security groups

### Advanced EC2 management

### AWS Batch

[AWS Batch](https://docs.aws.amazon.com/batch/)

### Elastic Container Service (ECS)

[AWS Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html)

### Elastic Beanstalk environment

[AWS Elastic Beanstalk](https://docs.aws.amazon.com/elastic-beanstalk/)

### Elastic Container Registry (ECR)

[AWS Elastic Container Registry](https://docs.aws.amazon.com/ecr/)

### Elastic Kubernetes Services (EKS)

[AWS Elastic Kubernetes Service](https://docs.aws.amazon.com/eks/latest/userguide/what-is-eks.html)