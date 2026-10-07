# Broadcast Domains

An Ethernet broadcast is intended for devices in the local broadcast domain.

Routers separate Layer-2 broadcast domains.

A simple topology:

```text
LAN A ── Router ── LAN B
```

A broadcast generated in LAN A does not automatically become an Ethernet broadcast in LAN B.

## Why this matters

Broadcast domains affect:

- ARP behavior
- scalability
- segmentation
- troubleshooting
- VLAN design

## VLAN preview

VLANs allow multiple logical Layer-2 networks to share switching infrastructure while remaining separate broadcast domains.
