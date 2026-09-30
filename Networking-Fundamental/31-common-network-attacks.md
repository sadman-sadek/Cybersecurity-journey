# 31 — Common Network Attacks

Study attacks as **failure of a security assumption**.

## Layer 2

- ARP spoofing
- MAC spoofing
- rogue DHCP
- VLAN-related misconfiguration/abuse
- rogue access points

## Layer 3

- IP spoofing
- route manipulation
- ICMP abuse

## Layer 4

- port scanning
- SYN flooding
- connection exhaustion
- reset abuse

## Application/network-service layer

- DNS poisoning
- DNS tunneling
- HTTP request abuse
- SSH brute-force attempts
- malicious proxy behavior

## Defensive framework

For every technique:

```text
Prerequisite
↓
Normal behavior
↓
Abnormal behavior
↓
Observable evidence
↓
Preventive control
↓
Detective control
↓
Recovery
```

Only reproduce attacks against authorized systems.
