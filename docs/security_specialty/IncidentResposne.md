# Incident Response Domain

## AWS Guard Duty

AWS Guard Duty is a threat intelligence service, which monitors for malicious behaviour to help customers protect their AWS workloads.

- Cloud Trail Events
- VPC Flow Logs
- DNS Logs

Threat Detection

- Trojans
- SSH Bruteforce
- Crypto Mining


## Understanding Incident Response Terminology.

What is an incident?

***Incident in security terminology is an event that poses a threat to information or computer security.***

Some of the sample incidents can be related to unauthorized access, attempts(failed/success) to break into systems, theft or loss of equipment that contains sensitive information.

What is Incident Response?

***Incident Response is an organized approach to address and manage the aftermath of a security incident in an organization.***

The goal is to handle the situation in a way that:

- limits damage
- reduces recovery time
- reduces cost

Is your organization ready?

- Detect brute froce attck on your servers?
- Identifying when someone makes changes to critical files?
- Identify if servers are sending traffic to critical files?
- Identify if someone is trying web application based attacks?
- Track on what exaclty users are doing within your network?
- Identify when someone is scanning your network?


## Incident Response - Use Cases

Evaluate the suspected compromised instances or exposed access keys.

### Exposed AWS Access & Secret Keys

Exposed AWS Access keys is one of the very common use-cases that you will find across many organizations.

There are certain steps which AWS recommends in such scenario:

1. Determine the acccess associated with those keys

```
Determine the acccess associated with those keys
```
2. Invalidating the credentials

```
Invalidating the credentials

Disable or delete the credentials, any application using them might be affected.

Ideally, disabling credentials is recommended instead of deleting (can be enabled back.)
```

3. Invalidating any temporary credentials issued with the exposed keys

```
Invalidating any temporary credentials issued with the exposed keys.

Even if we disable/delete Access keys, attackers may be able to perform actions using temporary access keys.

aws sts get-session-token
These credentials can have lifetime from (15 minutes) to 129600 seconds (36 hours).

In order to prevent this we can create an ExplictDeny Policy.
```

4. Restore access with new credentials.

```
- Consider using a new pair of access/secret keys.
- Instead of using long term keys, consider using IAM roles or federation.
```

5. Review your AWS account.

```
Review all the available s3 data and cloudTrail logs.
```

### Compromised EC2 instances

There are certain recommended steps in such scenario:

1. Lock the instance down

```
We isolate the EC2 instance so that it cannot contact the outside world.
Only access to the EC2 instance should be for forensic purposes.

e.g Remove all security groups.
Automation is a key aspect here.
```

2. Take the EBS snapshot

```
EBS Snapshot wll help ensure that all files in the server will be snapshotted.
```

3. Memory Dump.

```
All processes running in memory should be dumped.
```

4. Perform Forensic Analysis.

5. Terminate the instance.

```
Once forensics are done and RootCauseAnalysis (RCA) is released, we can go and terminate the EC2 instance.
```

## Incident Response in Cloud

AWS provides various visibility, security and automation controls tha can help us overall in the incident response process.

When we use cloud, many of the things related to proactivly detection, reaction and recovery can be easier in much more faster and cost effective way.

With help of various tools like ***AWS Config***, ***CloudTrail***, ***Guard Duty***, ***Cloudwatch*** and many more, we can easily track, monitor and analyze security related events.

Incident Response plan has several steps:

- Preparation

```
We need to make sure controls are in place that will help us in detection of anomalies with the infrastructure.

- Ensure logging is enabled with help of CloudTrail, VPC Flow Logs, EC2 Instances.
- Using AWS organizations to seperate accounts to reduce the blast surface.

```
- Detection

```
If you don't know if something is going wrong, you will not be able to respond to it (Capetan Obvious).

Use behavioural based by identifying or detecting breaches.
```

- Containment
- Investigation
- Recovery
- Lessons Learned
