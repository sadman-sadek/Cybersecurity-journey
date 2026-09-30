# 03 — Networking Big Picture

## Network = endpoints + links + forwarding + protocols + policy

A useful model:

```text
Endpoints
   |
Access network
   |
Switching
   |
Routing
   |
Security boundary
   |
Services
```

## LAN vs WAN

### LAN

Usually a local broadcast domain or collection of local segments.

Examples:

- home network
- office VLAN
- lab network

### WAN

Connects geographically separated networks.

Examples:

- enterprise WAN
- ISP network
- Internet

## Core device roles

| Device | Main job |
|---|---|
| NIC | Connect endpoint to network |
| Hub | Repeats bits/signals |
| Switch | Forwards frames using L2 information |
| Router | Forwards packets between networks |
| Firewall | Enforces traffic policy/state |
| Access Point | Bridges wireless clients into a network |
| Load balancer | Distributes application traffic |
| Proxy | Intermediates application connections |

## Broadcast domains

A key security idea:

**A broadcast domain is not the same thing as an IP subnet in every possible architecture, but VLANs commonly create L2 broadcast boundaries.**

You need to understand both concepts rather than treating them as synonyms.
