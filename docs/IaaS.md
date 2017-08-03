# Infrastructure as a Service (IaaS)

## Amazon Web Services

Subsections:
- [AWS Overview](#aws-overview)
- [AWS Shared Responsibility Model](#aws-shared-responsibility-model)

### AWS Overview

__Amazon Web Services (AWS)__ is a secure cloud service provider. It offers vast 
selection of services including computing power, storage, content delivery and 
others to help businesses scale and grow efficiently. 

AWS is [HIPAA compliant](https://aws.amazon.com/compliance/hipaa-compliance/) 
and can be used to process, store and transmit ePHI. This however apply certain 
restrictions on used services and requires specific measures aimed to secure 
your infrastucture. Usage of AWS _does not automatically make your cloud 
infrastructure HIPAA compliant_.

AWS offers subset of their services as __HIPAA eligible__. Usage of other 
services outside of this list is not allowed. Full list is available on their 
[HIPAA Eligible Services 
Reference](https://aws.amazon.com/compliance/hipaa-eligible-services-reference/) 
page. This list is changing over time as AWS adds HIPAA eligibility for more 
services, check AWS reference page to get latest details. 

Currently (at the time of writing) following services are HIPAA eligible:
- Amazon API Gateway excluding the use of Amazon API Gateway caching
- Amazon Aurora [MySQL-compatible edition only]
- Amazon CloudFront [excluding Lambda@Edge]
- Amazon Cognito
- AWS Database Migration Service
- AWS Direct Connect
- AWS Directory Services excluding Simple AD and AD Connector
- Amazon DynamoDB
- Amazon EC2 Container Service (ECS)
- Amazon EC2 Systems Manager
- Amazon Elastic Block Store (Amazon EBS)
- Amazon Elastic Compute Cloud (Amazon EC2)
- Elastic Load Balancing
- Amazon Elastic MapReduce (Amazon EMR)
- Amazon Glacier
- Amazon Inspector
- Amazon Redshift
- Amazon Relational Database Service (Amazon RDS) [MySQL, Oracle, and PostgreSQL 
  engines only]
- AWS Shield [Standard and Advanced]
- Amazon Simple Notification Service (SNS)
- Amazon Simple Queue Service (SQS)
- Amazon Simple Storage Service (Amazon S3) [including S3 Transfer Acceleration]
- AWS Snowball
- Amazon Virtual Private Cloud (VPC)
- AWS Web Application Firewall (WAF)
- Amazon WorkDocs
- Amazon WorkSpaces

_Business Associate Agreement (BAA)_, or _Business Associate Addendum_ (as AWS 
reference it) need to be signed before you can start usage of AWS for your HIPAA 
compliant workloads.

AWS implements _shared responsibility model_ where AWS manages security "of the 
cloud" and leave security "in the cloud" to be managed by the customer.

AWS offers a HIPAA-focused Whitepaper [Architecting for HIPAA Security and 
Compliance on Amazon Web 
Services](https://d0.awsstatic.com/whitepapers/compliance/AWS_HIPAA_Compliance_Whitepaper.pdf):
it has good overview of all HIPAA eligible services and explains how they can be 
used for building systems processing health information.

As a summary, here is a list of __steps to HIPAA compliant AWS infrastructure__:
1. Understand _shared responsibility model_
1. Sign _BAA (Business Associate Addendum)_
1. Use _HIPAA eligible services_ to build your infrastructure
1. Make sure your AWS services _configuration is HIPAA compliant_ (this is 
   customer's part of the shared responsity model) 

### AWS Shared Responsibility Model

AWS implements _shared responsibility model_ where AWS manages security "of the 
cloud" and leaves security "in the cloud" to be managed by the customer. It 
means there are two categories of security measures applied.

- __Security of the cloud:__ security measures that the cloud service provider 
  (AWS) implements and operates

- __Security in the cloud:__ security measures that the customer implements and 
  operates, related to the security of customer content and applications that 
  make use of AWS services

Basically AWS provides infrastrucuture for your applications that _can be used 
in HIPAA compliant way_. But it's your (AWS customer) responsibility to 
_configure cloud infrastructure_ to ensure confidentiality, integrity and 
availability of ePHI. You are also responsible for security of the 
application(s) deployed on top of this HIPAA compliant cloud infrastructure.

Following diagram demostrates this partitioning of responsibility.

![AWS Shared Responsibility Model](../img/aws-shared-responsibility-model.png)

AWS as a cloud service provider manages _physical security_ of the following 
components.

- Regions and availability zones
- Edge locations
- Compute resources
- Storage resources
- Databases
- Networks

You as a _customer manage security_ of the following areas.

- Network traffic protection
- Server-side encryption (for storage and databases)
- Data transmission integrity and encryption 
- Data availability
- Disaster recovery
- Access management

All these areas are typically covered by the cloud service provider (AWS) 
offerings but require proper _cloud architecture and configuration_ to be 
implemented by the customer.

Additionally you are responsible for security of components deployed on top of 
your AWS cloud infrastructure.

- Operating systems
- Platforms
- Applications

Understanding of the _shared responsibility model_ is an important step towards 
running your HIPAA application in AWS cloud. You can clearly see the boundaries 
of AWS offering in terms of security and plan your cloud architecture 
accordingly.

### AWS BAA

### AWS Security In Transit

### AWS Security At Rest

### AWS Network security

### AWS Availability

### AWS Disaster Recovery

### AWS Access Management



## Google Cloud Platform

_Coming soon..._




## Microsoft Azure

_Coming soon..._
