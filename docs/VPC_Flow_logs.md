# VPC Flow Logs

VPC Flow logs is feature that enables you to capture information about the IP traffic going to and from network interfaces in your VPC.

Flow log data is stored using AWS CloudWatch Logs. After you've created a flow log you can view and retrieve it's data in Amazon CloudWatch Logs.

Flow Logs can be created at 3 different levels:

1.  VPC
2.  Subnet
3.  Network Interface Level

## Tips

- You cannot enable flow logs for VPCs that are peered with your VPC, unless the VPC peer is in **your AWS account**
- You cannot tag a flow log.
- After creation of a flow log, you cannot change it's configuration (e.g associate it with a different IAM role).
- You can stream these logs to Lamdba or Elasticsearch Engine.

## Not all traffic is monitored

1.  Amazon DNS
2.  Windows Activation
3.  Traffic from and to 169.254.169.254
4.  DHCP traffic
5.  Traffic to the reserved IP address for the VPC router
