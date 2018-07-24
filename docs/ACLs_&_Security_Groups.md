# Network Access Control Lists vs Security Groups

- Your VPC automatically comes with a default network ACL, and by default allows all outbound and inbound traffic.
- By Default when you create an AC everything is DENIED.
- ACL Rules are evaluated in numerical order (100 < 101).
- You can associate a subnet with one Network ACL.
- If you don't explicity associate a subnet with a network ACL, the subnet is automatically associated with the default ACL
- Network ACLs are **stateless**. Responses to allowed inbound traffic are subject to the rules for outbound traffic (and vice versa)

1.  You have to open ephemeral ports at Outbound Rules.

2.  You can Block IPs with ACLs not Security Groups.

3.  Security Groups are **stateful**.
