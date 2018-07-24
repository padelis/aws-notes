# Bastion Hosts (Jumpboxes)

Allows you to SSH to a Bastion Host and then initiate a private connection over the private network to administer them.

Bastions are used for administration.

NAT Instances are **always** behind a security group (NAT gateways **NOT**).


How to make a bastion instance highly available?
- Multiple subnets (at least two public subnets one bastion at each subnet)

## Tips

- A NAT instance is used to provide internet traffic to EC2 instances in private subnets
- A Bastion instance is used to securely administer EC2 instances (SSH or RDP) in private subnets.
