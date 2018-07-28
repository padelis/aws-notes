# Simple Notification Service

Amazon Simple Notifcation Service (Amazon SNS) is a web service that makes it easy to set up, operate and send notifications from the cloud.

Deliver Notifications to Subscribers.
Push Notifications to:

- Apple
- Google
- Fire OS
- Windows
- Android Devices

SNS Can also deliver SMS Text Messages or email, or **trigger lambda functions**.

**Push Messaging System**.

SNS Allows you to group multiple recipients using topics.
A topic is an `access point` for allowing recipients to dynamically subscribe for identical copies of the same notification.

For example you can group together iOS, and Android and SMS recipients. When you publish once to a topic, SNS delivers appropriately formatted copies to each subscriber.

Use cases:

- CloudWatch
- Auto scaling groups
- Billing Alarms

## SNS Subscribers

- HTTP
- HTTPS
- Email
- Email json
- SQS
- Application
- Lambda

## Benefits of SNS

- Instantaneous, push-based delivery (no polling, like SQS)
- Simple APIs
- flexible message delivery groups
- Inexpensive, pay-as-you model with no up-front costs

## SNS vs SQS

- Both Messaging Service
- SNS - Push
- SQS - Polls (Pulls)

## Pricing

- Users pay $0.50 per 1 million Amazon SNS Requests
- $0.06 per 100.000 Notification deliveries over HTTP
- $0.75 per 100 SMS
- $2.00 per 100.000 deliveries over Email
