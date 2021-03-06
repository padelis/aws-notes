# Virtual Private Cloud Overview

## Virtual Data center in the cloud

Amazon VPC lets you provision a logically isolated section of the AWS Cloud where you can launch AWS resources in a **virtual network that you define**. You have complete control over your virtual networking environment, including selection of your own IP address range, creation of subnets, and configuration of route tables and network gateways.

You can easily customize the network configuration for your AWS Virtual Private Cloud. For example, you can create a **public-facing subnet** for your Web Servers that has access to the Internet, and place your backend systems such as databases or application servers in a **private facing subnet** with no Internet access. You can leverage multiple security layers, including security groups and network access control lists, to help control EC2 instances in each subnet.

Additionally, you can create a Hardware Virtual Private Network (VPN) connection between your corporate data center and your VPC and leverage the AWS cloud as an extension of your corporate datacenter.

**One subnet equals one AZ**.
**Every region has it's default VPC**.

Three Classes:

- 10.0.0.0 - 10.255.255.255 (10/8 prefix)
- 172.16.0.0 - 172.31.255.255 (172.16/12 prefix)
- 192.168.0.0 - 192.168.255.255 (192.168/16 prefix)

## What you can do with VPC:

- Launch instances into a subnet
- Assign custom IP address ranges in each subnet
- Configure route tables between subnets
- Create an Internet gateway and attach it to your VPC (**One per VPC**)
- Much better security control over your AWS resources.
- Instance security groups (span across AZ, not VPCs)

## Default VPC vs Custom VPC

- Default is user friendly, allowing you to immediatly deploy instances
- All subnets in default VPC have a route out to the internet
- Each EC2 has both a public and a private IP.
- Public IPs are not managed.
- New subnets within a custom VPC can communicate with each other, across AZ's

## VPC Peering

- Allows you to connect one VPC with another via a direct network route using **private IP address**
- Instances behave as if they were on the same private network
- You can peer VPC's with other AWS accounts as well as with other VPCs in the same account.
- Peering is always in **STAR** configuration. There is **no transitive peering**

## Tips

- Think of a VPC as logical datacenter in AWS.
- Consists of IGWS (Or Virtual Private Gateways), Route Tables, Network Access Control Lists, Subnets and Security Groups
- **1 subnet = 1 AZ**
- Security Groups are **Stateful**, Network Access Control Lists are **Stateless** (Inbound and Outbound)
- No transitive peering.

## Reserved Addresses - 5 Addresses

The first four IP addresses and the last IP address in each subnet CIDR block are not available for you to use, and cannot be assigned to an instance. For example, in a subnet with CIDR block 10.0.0.0/24, the following five IP addresses are reserved:

10.0.0.0: Network address.

10.0.0.1: Reserved by AWS for the VPC router.

10.0.0.2: Reserved by AWS. The IP address of the DNS server is always the base of the VPC network range plus two; however, we also reserve the base of each subnet range plus two. For VPCs with multiple CIDR blocks, the IP address of the DNS server is located in the primary CIDR. For more information, see Amazon DNS Server.

10.0.0.3: Reserved by AWS for future use.

10.0.0.255: Network broadcast address. We do not support broadcast in a VPC, therefore we reserve this address.

## VPC and ELB

You need your application load balancers to always be at least **two** AZ. These AZs must be public.

## VPC End Points (Don't go through Internet)

Endpoint come in two different varieties:

1.  Interface Endpoint (Elastic Network Interface - A point of entry for your traffic)
2.  Internal Gateway Endpoint (Highly Available to all the different services)

## VPC peering

A connection between two VPCs that enables you to route traffic between them, using private and public IPs

- They have to be in **the same region**.
- They can't have matching or overlaping CIDR blocks.
- Transitive Peering not supported

## Direct Connect

A dedicated line from your premises to AWS.

- Reduce costs when using large volumes of data
- Increase reliability
- Increase bandwidth

VPN vs Direct connect.

VPN is up in minutes and goes over the internet.
