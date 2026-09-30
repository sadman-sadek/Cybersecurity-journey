# 25 — Packet Analysis

Packet analysis is the bridge between networking knowledge and cybersecurity.

## Your first question

**What am I looking at?**

Identify:

```text
Ethernet
  ↓
IPv4/IPv6
  ↓
TCP/UDP/ICMP
  ↓
Application protocol
```

## Packet vs frame vs segment

Use precise language:

- frame: Layer 2
- packet: Layer 3
- segment: commonly TCP Layer 4
- datagram: commonly UDP/other contexts

## Analysis workflow

1. Determine capture point.
2. Identify hosts.
3. Follow conversations.
4. Identify protocol.
5. Inspect flags.
6. Check timing.
7. Check retransmissions.
8. Check errors.
9. Compare directions.
10. Form a hypothesis.
11. Find evidence.

## Never trust one packet

A single packet rarely tells the entire story.

Look for:

- previous packets
- next packets
- related DNS
- related TCP handshake
- response traffic
- retransmissions
- resets
- timing
