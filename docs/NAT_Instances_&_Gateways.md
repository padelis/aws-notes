# NAT Instances & NAT Gateways

## NAT instances

- When creating a NAT instance, Disable Source/Destination Check on the instance.
- NAT instances must be in a public subnet
- There must be a **route out of the private subnet to the NAT, in order for this to work**.
- The amount of traffic that NAT instances can support depends on the instance size. If you are bottlenecking, increase the instance size.
- You can create high availability using Autoscaling Groups, multiple subnets in different AZs, and a script to automate failover.
- NAT Instances are behind a security group

## NAT Gateway

- Preferred by the enterprise
- Scale automatically up to 10Gbps
- No need to patch
- Not associated with security groups
- Automatically assigned a public IP address
- Remember to update your route tables
- No need to disable Source/Destination Checks
- More secure than a NAT instance.
- Having one NAT Gateway in one AZ is not good enough for redundancy.
- You don't have SSH access
