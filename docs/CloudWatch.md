# CloudWatch

- Standard Monitor - 5 minutes
- Detailed Monitor - 1 minute

1.  Dashboards (RAM Consumption is not included by default)
2.  Alarms (Thresholds)
3.  Event responds to State Changes (e.g Lambda Functions)
4.  Aggregate, monitor and store logs.
5.  **Can** be used on premise with SSM agent and CloudWatch Agent.
6.  Minimun granularity is 1 minute.
7.  CloudWatch Logs are stored indefinitely.

CloudWatch is used for **Performance Monitoring**.  
CloudTrail is used for **Auditing**.

## EC2 Metrics

- CPU
- Network
- Disk
- Status Check

## EBS Metrics

- Volume Read Ops
- Volume Write Ops
- Volume Queue Length
- Volume Status (I/O Performance Status)
  - Normal
  - Degraded/Severely Degraded (*Warning*)
  - Stalled (**Impaired**)
