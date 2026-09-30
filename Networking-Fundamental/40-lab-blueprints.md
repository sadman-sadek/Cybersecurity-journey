# 40 — Lab Blueprints

## Lab 1 — Two-host LAN

Learn:

- Ethernet
- MAC
- ARP
- IPv4
- ping

## Lab 2 — Two subnets + router

Learn:

- routing
- default gateway
- ARP
- TTL

## Lab 3 — VLAN segmentation

Learn:

- access ports
- trunking
- VLANs
- inter-VLAN routing

## Lab 4 — DNS + DHCP

Learn:

- leases
- DNS resolution
- packet capture

## Lab 5 — Firewall

Learn:

- state
- allow/deny
- logging

## Lab 6 — VPN

Learn:

- tunnel
- routes
- encryption boundary

## Lab 7 — IDS

Learn:

- normal traffic
- suspicious patterns
- alerts

## Lab 8 — Enterprise mini-network

```text
                    Internet
                       |
                    Firewall
                  /    |     \
               DMZ   Users   VPN
                |      |
             Web/App  Switch
                       |
                 Servers VLAN
                       |
                Management VLAN
```

## Lab 9 — Blue-team incident

Generate benign suspicious behavior in your isolated lab:

- repeated failed connections
- unusual DNS requests
- internal service enumeration
- unexpected management connection

Then investigate from logs and packet captures.

## Lab documentation template

```text
Objective:
Topology:
Addresses:
Devices:
Expected traffic:
Actual traffic:
Capture:
Failure introduced:
Evidence:
Root cause:
Fix:
Security lesson:
```
