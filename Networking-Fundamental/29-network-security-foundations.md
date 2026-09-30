# 29 — Network Security Foundations

## CIA

Networking supports:

- Confidentiality
- Integrity
- Availability

## Attack surface

Network attack surface includes:

- exposed services
- management interfaces
- routing protocols
- wireless
- DNS
- remote access
- VPN endpoints
- firewalls
- cloud gateways
- containers
- APIs

## Trust boundaries

Draw them.

Example:

```text
Internet
  |
[Firewall]
  |
DMZ
  |
[Internal Firewall]
  |
Internal
  |
Management
```

## Security controls

Understand the role of:

- segmentation
- ACLs
- firewalls
- IDS/IPS
- proxies
- VPNs
- authentication
- encryption
- logging
- network access control
- secure configuration

## Threat-modeling question

For every link:

```text
Can an attacker observe it?
Can they inject traffic?
Can they spoof identity?
Can they exhaust resources?
Can they bypass policy?
Can we detect abnormal behavior?
```
