# 37 — Cloud Networking

Cloud networking is still networking.

You will see familiar ideas with new abstractions.

## Learn these concepts

- VPC/VNet
- subnet
- route table
- internet gateway
- NAT gateway
- security group
- network ACL
- load balancer
- private endpoint
- peering
- transit gateway/router concepts

## Mental translation

Traditional:

```text
VLAN → subnet → router → firewall
```

Cloud:

```text
virtual network → subnet → route table → security policy → gateway
```

The implementation differs; the reasoning remains.

## Security checklist

Ask:

- Which workloads are public?
- Which are private?
- What routes exist?
- Which identities can modify network policy?
- Is east-west traffic controlled?
- Where are logs?
- Is IPv6 enabled?
- Are security rules overly broad?

## Lab

Draw a three-tier application:

```text
Internet
   |
Load Balancer
   |
Web subnet
   |
App subnet
   |
Database subnet
```

Define permitted flows before creating anything.
