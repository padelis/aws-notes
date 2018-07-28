# Application Services Summary

## Simple Queue Service

Amazon is a web service that gives you access to a message queue, that can be used to store messages while waiting for a computer to proccess them.
Amazon SQS is a distributed messaging queue (one component generates and another component consumes).

- EC2 instances poll SQS for work.
- SQS is a pull base system (SNS is push base system)
- SQS is a great way to decouple your infra.
- Up to 256KB of messages in any format.
- Messages are retrieved using the SQS API
- Messages can be kept from 1 minute to 14 days, **default is 4 days**

You can build auto scaling groups to handle messages (**queue acts as a buffer**)

### Visibility Timeout

Visibility timeout is the amount of time that a message is invisible in the queue after a **reader** picks it up. If the job is not processed within this time the message will become visible again.

- Default Visibility Timeout is **30 seconds**
- Maximum is **12 hours**

## SQS vs SWF

SQS represents a **message oriented API**
SWF represents a **task oriented API**

SQS has a retention of 14 days,
SWF up to a year for workflow executions.

SWF ensures that a task is **assigned only once**.
With SQS you have to handle duplicate messages

SWF keeps tracks of all tasks and events
With SQS you need to implement your own application-level tracking.

### SWF Actors

- Workflow starters (An application that can start a workflow)
- Deciders (Control the flow)
- Activity Workers (Can be humans)

## SNS Subscribers

- HTTP
- HTTPS
- Email
- Email json
- SQS
- Application
- Lambda

### SNS vs SQS

- Both Messaging Service
- SNS - Push
- SQS - Polls (Pulls)

## Elastic Transcoder

Media Transcoder in the cloud.
Convert media files from their original source format in to different formats that will play on other devices

Pay based on the minutes you transcode and the resolution at which you transcode.

## Kinesis Streams

Data producers send data to Kinesis Streams. It's stored in Shards for 24 Hour - 7 Days Retention

The capacity of your stream is a function of the number of shards that you specify for your stream. The total capacity of the streams is the sum of the capacities of its shards.
Shards pipe the data to Data Consumers.

Consumers can store data to DynamoDB or S3

## Kinesis Firehose

It's completely automated. You can analyze data with Lambda in real time and then send them to S3 or other locations.

You don't have retention. Data send to Firehose are already analyzed.

**Quering with Lambda**

No consumers. No shard management.
