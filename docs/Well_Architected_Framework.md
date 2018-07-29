# Well Architected Framework

General Design Principles

- Stop guessing your capacity needs
- Test systems at production scale
- Automate to make architectural experimentation easier
- Allow for evolutionary architectures
- Data-Driven architectures
- Improve through game days

## Security

### Design Principles

- Apply security at all layers
- Enable traceability
- Automate responses to security events
- Focus on securing your system
- Automate security best practices (e.g OS Hardening)

### AWS Shared Responsibility Model

Customer are responsible for:

- Their Data
- Platforms, Apps, IAM Configuration
- Operating System, Network & Firewall
- Client-side Data Encryption & Data Integrity
- Server-side Encryption
- Network Traffic Protection

AWS responsible for:

- Compute, Storage, Database, Networking
- Global infrastructure (Regions, Availability Zones, Edge Locations)

### Definition & Best Practices

Security in the cloud consists of 4 areas:

- **Data protection**
  - You have to **classify** your data into segments.
  - You have to implement a **privilege access system**
  - **Encrypt** everything where possible
- **Privilege management**
  Ensure that only authorized and authenticated user are able to access your resources.
  - Access Control Lists
  - Role Based Access Controls
  - Password Management
- **Infrastructure protection** at VPC Level
- **Detective controls**
  - AWS CloudTrail (Regional Service)
  - AWS CloudWatch
  - AWS Config
  - S3
  - Glacier

### Key AWS Services

Security in the cloud consists of 4 areas:

- Data protection
  - EBS, S3 & RDS
- Privilege management
  - IAM, MFA
- Infrastructure protection
  - VPC
- Detective controls
  - AWS CloudTrail (Regional Service)
  - AWS CloudWatch
  - AWS Config
  - S3
  - Glacier

## Reliability

### Design Principles

- Test recovery procedures
- Automatically recover from failure
- Scale horizontally to increase aggregate system availability (scale out)
- Stop guessing capacity

### Definition & Best Practices

Reliability consists of three areas:

- **Foundations** - Service Limits
- **Change Management**
  - You can use CloudWatch to monitor your environment and Autoscaling in response to changes to your environment
- **Failure Management**
  - You should become aware of these failures, how they occured, how to respond to them and then plan on how to prevent these from happening

### Key AWS Services

- Foundations
  - IAM, VPC
- Change Management
  - CloudTrail
- Failure Management
  - CloudFormation

## Performance Efficiency

How to use computing resources efficiently to meet your requirements and how to maintain that efficiency as demands changing and technology evolves

### Design Principles

- Democratize advanced technologies
- Go global in minutes
- Use server-less architecture

### Definition & Best Practices

- Compute
  - Select the right type of server type (or no servers at all)
- Storage
  At AWS storage is virtualized. With s3 you can have 11x9's durability. With EBS you can choose different storage mediums (such as SSD, Magnetic, PIOPS etc).
  - Access Method (Block, file, or Object)
  - Patterns of Access - Random or Sequential
  - Throughput Required
  - Frequency of Access
  - Frequency of Update
  - Availability Constraints
  - Durability Constraints
- Databases
  At AWS you can use the global infrastructure to have multiple copies of your data. You can also use caching services (Elasticache or CloudFront) to reduce latency.
- Space Time trade-off

### Key AWS Services

- Compute
  - Autoscaling
- Storage
  - EBS, S3, Glacier
- Databases
  - RDS, DynamoDB, Redshift
- Space Time trade-off (Anything that reduces latency)
  - CloudFront, ElastiCache, Direct Connect

## Cost Optimization

Reduce your costs to a minimum and use those savings for other parts of your business. A cost optimized system allows you to pay the lowest price possible while still achieving your business objectives

### Design Principles

1.  Transparently attribute expenditure
2.  Use managed services to reduce cost of ownership
3.  Trade capital expense for operating expense
4.  Benefit from economies of scale
5.  Stop spending money on data center operations

### Definition Best Practices

Cost Optimization in the cloud consists of 4 areas:

- Matched supply and demand
  - You have align supply a demand. Autoscaling or Lambda
  - CloudWatch, helps you keep track.
- Cost Effective resources
  - Using the correct instance type can be key to cost savings.
- Expenditure Awareness
  - Being aware of what each team is spending and where is crucial. Tag Everything & Set-up Billing Alerts.
- Optimizing Over time
  - You should keep track of changes made to AWS and constantly re-evaluate your existing architecture.

### Key AWS Services

- Matched supply and demand
  - Autoscaling
- Cost Effective resources
  - EC2 reserved instances, Trusted Advisor
- Expenditure Awareness
  - CloudWatch Alarms, SNS
- Optimizing Over time
  - Trusted Advisor.

## Operational Excellence

Includes operational practices and procedures used to manage production workloads.

### Design Principles

1.  Perform operations with code
2.  Align operations processes to business objectives (collect metrics)
3.  Make small incremental changes
4.  Test for responses to unexpected events
5.  Learn from operational events and failures
6.  Keep operational procedures up to date

### Definition & Best Practices

- **Preparation**
  - Workloads should have:
    1.  Runbooks - operation guidance to perform daily tasks
    2.  Playbook - guidance to unexpected operational events
  - Documentation
- **Operations**
  - Should be standardized on a routine basis. The focus should be on automation. Avoid manual executions.
  - Set up CI/CD. Release management processes
- **Responses**
  - Responses to unexpected events should be automated.

### Key AWS Services

- Preparation
  - AWS Config, AWS Catalog, SQS
- Operations
  - CodeCommit, CodeDeploy CodePipeline, CloudTrail
- Responses
  - CloudWatch, SNS
