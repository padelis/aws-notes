# EC2 Summary & Tips

## Pricing Groups:

- On Demand Instances
- Spot Instances (If you terminate them you pay)
- Reserved Instances (Contracts)
- Dedicated Hosts

## Elastic Block Storage consists of:

- SSDs, GP2(**10000 IOPS**)
- SSDs Provisioned (**More than 10000 IOPS**)
- HDDs Throuput Optimized
- HDDs Cold Storage
- HDDs Magnetic

You cannot mount 1 EBS volume to multiple instances.

- Termination Protection is off by default
- On a EBS-backed instance upon termination the default action is to delete the root EBS volume (**unless if instructed when creating**)
- Root volumes can now be encrypted (Take snapshot and encrypt) via the AWS API or third party tools (bit locker)
- Aditional Volumes can be encrypted.

## Volumes vs Snapshots

- Volumes exist on EBS
- Snapshots exist on S3
- Snapshot are point in time copies of volumes.
- Snapshots are incremental

### Snapshots Security

- Snapshots are encrypted automatically
- Volumes created from encrypted snapshots are encrypted.
- Snapshot can be **shared** if they are **unencrypted**.

## Snapshots of Root Device Volumes

```
ec2-create-snapshot
```

- To create a snapshot of a root volume you have to stop the instance.
- To [delete a snapshot of an EBS Volume that is used as the root device of a registred AMI](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-deleting-snapshot.html), you have to **deregister** the AMI first.

## EBS vs Instance store

- Instance store is ephemeral storage.
- If the host fails you lose instance store data.
- EBS can be stopped. You will not lose the data.
- You can reboot **both**
- Both will be deleted on termination. (You can keep EBS backed)

## Take a snapshot of a RAID Array

- Stop the application from write to the disk
- Flush all caches to disk
  - Freeze the file system
  - Unmount the RAID array
  - Shutdown the EC2 instance

## Amazon Machine Images

- AMIs are regional.
- You can launch an AMI from the region it's stored.
- You can copy AMIs to other regions using console, command line or the Amazon EC2 API.

## Monitoring

Standard Monitoring = **5 Minutes**
Detailed Monitoring = **1 Minute**

CloudWatch is used for **Performance Monitoring**.
CloudTrail is used for **Auditing**.

### CloudWatch

- Dashboards
- Alarms (**Thresholds**)
- Events (respond in **State Changes**)

## Roles

Are far more secure than storing the **access key** and **secret access key** on individual EC2 instances

Roles are easier to manage
Roles are universals (Everything in IAM is universal)
Roles can be assigned after the EC2 instance has been Provisioned

## Instance Meta-data

Used to get information about an instance(r.g public ip).

```
curl http://169.254.169.254/latest/meta-data
```

```
curl http://169.254.169.254/latest/user-data
```

## Elastic File System

- Supports NFSv4
- You only pay what you use.
- Can scale to petabytes
- Data is stored across multiple AZ's within region
- It is block base storage - not object base.
- Can support thousands concurrent connections
- Read After Write Consistency

## Lambda

A compute Service where you can upload your code and create a lambda function.

Can be used in the following ways:

1.  As an event driven compute service, where the code runs in **response of events**.

- Changes to S3 Bucket.
- Changes to a DynamoDB Table

2.  As an event driven compute service, where the code runs in **response of HTTP requests**

- Amazon API Gateway
- AWS SDKs

## Placement groups

- Clustered Placement Group (one AZ - Big Data)
  - Used for EC2 instances that require **high network traffic** and **low latency** across a single availability zone.
- Spread Placement Group (Distinct Hardware)
