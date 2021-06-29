# Cloud Services Overview

[LinkedIn Learning Video Course: Cloud Services Overview](https://www.linkedin.com/learning/aws-certified-solutions-architect-associate-saa-c02-1-cloud-services-overview?contextUrn=urn%3Ali%3AlyndaLearningPath%3A5f0f83ce498e4916ed6c9b22)

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

