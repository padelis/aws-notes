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

## Supported Languages

1. Node.js (18.x, 20.x)
2. Java (8, 11, 17, 21)
3. C# (.NET 6, .NET 8)
4. Python (3.8, 3.9, 3.10, 3.11, 3.12)
5. Go (1.x)
6. Ruby (3.2)
7. PowerShell (7.4)
8. Custom Runtime (Any language)

## Pricing

- Number of requests (1M requests $0.20)
- Duration: Price depends on the amount of Memory allocated
- Provisioned Concurrency: $0.0000041667 per GB-second
- Duration: $0.0000166667 per GB-second (on-demand)

## So cool

- No servers
- Continuous scaling
- Cheap

## Key Features & Limits

- Scales **out** not up
- 1 event = 1 function
- Multiple Lambda functions can be triggered from one event
- **AWS X-Ray** allows debugging and tracing
- Can do things globally (e.g Backup S3 Buckets)
- Maximum execution time is **15 minutes** (increased from 5 minutes)
- Maximum memory: 10,240 MB (10 GB)
- Maximum package size: 250 MB (unzipped), 50 MB (zipped)
- Concurrent executions: 1,000 per region (can be increased)

## New Features (2024)

- **Lambda SnapStart** - Faster cold starts for Java functions
- **Lambda Powertools** - Developer productivity tools
- **Lambda Extensions** - Custom runtimes and monitoring
- **Container Images** - Deploy Lambda functions as container images
- **Function URLs** - Direct HTTP endpoints without API Gateway
- **Lambda@Edge** - Run Lambda functions at CloudFront edge locations
- **Provisioned Concurrency** - Pre-warm functions for consistent performance
