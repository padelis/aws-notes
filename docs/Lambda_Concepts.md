# Lambda Concepts - Serverless

## Brief History

1.  Data Center
2.  IAAS (provision a machine with API call)
3.  PAAS (Elastic BeanStack)
4.  Containers
5.  Serverless

Lambda encapsulates:

- Data Centers
- Hardware
- Assembly
- High Level Languages
- OSs
- Application Layer/ AWS APIs
- AWS Lambda

**A compute Service where you can upload your code and create a lambda function**.

Can be used in the following ways:

1.  As an event driven compute service, where the code runs in **response of events**.

- Changes to S3 Bucket.
- Changes to a DynamoDB Table

2.  As an event driven compute service, where the code runs in **response of HTTP requests**

- Amazon API Gateway
- AWS SDKs

## Triggers

- Api Gateway (resolution with arn Amazon Resource Name)
- AWS Iot
- Alexa skill set
- Alexa Smart Home
- CloudWatch Events
- CloudWatch Logs
- CodeCommit
- Cognito Sync
- DynamoDB
- Kinesis
- S3
- SNS
- SQS

## Languages

1.  Node.js
2.  Java
3.  C#
4.  Python

## Pricing

- Number of requests (1m requests $0.20)
- Duration Price depends on the amount of Memory allocated

## So cool

- No servers
- Continuous scaling
- Cheap

## Tips

- Scales **out** not up
- 1 event = 1 function
- Multiple Lambda functions can be triggered from one event
- **AWS X-ray** allows debugging
- Can do things globally (e.g Backup s3 Buckets)
- Maximum execution time is **5 minutes.**
