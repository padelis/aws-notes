# Simple Queue Service

Amazon is a web service that gives you access to a message queue, that can be used to store messages while waiting for a computer to proccess them.
Amazon SQS is a distributed messaging queue (one component generates and another component consumes).

- EC2 instances poll SQS for work.
- SQS is a pull base system (SNS is push base system)
- SQS is a great way to decouple your infra.
- Up to 256KB of messages in any format.
- Messages are retrieved using the SQS API

You can build auto scaling groups to handle messages (**queue acts as a buffer**)

## Queue Types

1.  Standard Queue (default)
    - Nearly unlimited number of messages
    - Guarantee that the messages will be delivered at least one.
    - Best Effort Ordering
2.  Fifo (good for _strict order_)
    - First In/First Out
    - No duplicates
    - Message groups
    - 300 transactions per second

## SQS Key Facts

- Up to 256KB of messages in any format.
- SQS is a pull base system
- Default message retention is 4 days
- Messages can be kept from 1 minute to 14 days
- Guarantees that your messages will be processed at least once.

## Visibility Timeout

Visibility timeout is the amount of time that a message is invisible in the queue after a **reader** picks it up. If the job is not processed within this time the message will become visible again.

- Default Visibility Timeout is **30 seconds**
- Maximum is **12 hours**

## SQS Long Polling

Long polling doesn't return a response until a message arrives in the queue, or the **long poll times out**

**Long polling can save your money**
