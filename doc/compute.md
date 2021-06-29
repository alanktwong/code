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

### EC2 Instance Types

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