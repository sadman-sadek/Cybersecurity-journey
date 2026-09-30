# 14 — UDP and ICMP

## UDP

UDP is connectionless and lightweight.

Header essentials:

```text
Source port
Destination port
Length
Checksum
```

Applications can build their own reliability/ordering above UDP.

Examples include DNS and many real-time/modern protocols.

## ICMP

ICMP is used for control/error signaling and diagnostics.

Examples:

- Echo Request
- Echo Reply
- Destination Unreachable
- Time Exceeded

`ping` commonly uses ICMP Echo messages.

`traceroute`/`tracert` can use TTL/hop-limit behavior and different probe types depending on platform/mode.

## Security

Do not treat "ICMP = bad" as a rule.

ICMP can be:

- essential for network operation
- useful for diagnostics
- filtered for policy reasons
- abused for reconnaissance or covert channels

## Lab

Capture a ping and identify:

```text
Ethernet
IPv4/IPv6
ICMP
```

Then run a trace and compare the returned TTL-exceeded messages.
