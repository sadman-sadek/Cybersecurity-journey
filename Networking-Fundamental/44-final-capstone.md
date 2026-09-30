# 44 — Final Capstone: Build a Defensible Enterprise Network

You have been asked to design and monitor a fictional company network.

## Requirements

Company:

```text
500 employees
50 servers
2 public applications
remote workers
guest Wi-Fi
administrative network
central logging
```

## Your architecture

Include:

```text
Internet
  |
Edge
  |
Firewall
  |
DMZ
  |
Internal segmentation
 |       |        |
Users   Servers   Management
```

## Deliverable 1 — Address plan

Document:

- IPv4 subnets
- IPv6 strategy
- gateways
- reserved ranges
- management addresses

## Deliverable 2 — VLAN plan

Define:

- Users
- Servers
- Management
- Security
- Guest
- Voice/IoT if relevant

## Deliverable 3 — Routing

Document:

- default routes
- internal routes
- dynamic/static choices
- failure considerations

## Deliverable 4 — Security matrix

Create:

| Source | Destination | Protocol/Port | Action | Reason |
|---|---|---|---|---|

Every allowed flow needs a reason.

## Deliverable 5 — Monitoring

Collect:

- DNS
- firewall
- authentication
- flow
- IDS
- endpoint/network telemetry

## Deliverable 6 — Incident scenario

Investigate:

```text
A workstation begins contacting
hundreds of internal ports.
It then makes periodic outbound TLS connections.
DNS queries increase sharply.
```

Do not assume compromise.

Develop hypotheses and collect evidence.

## Deliverable 7 — Executive explanation

Explain the incident to a non-technical manager in five paragraphs.

Then explain the exact same incident to a network engineer using packet-level evidence.

## Graduation standard

You are not finished when you can recite definitions.

You are finished when you can:

```text
DESIGN
   ↓
BUILD
   ↓
CAPTURE
   ↓
EXPLAIN
   ↓
BREAK
   ↓
TROUBLESHOOT
   ↓
SECURE
   ↓
DETECT
   ↓
AUTOMATE
```

That is the networking foundation on which advanced cybersecurity skills can be built.
