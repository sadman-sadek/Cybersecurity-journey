# Encapsulation and Decapsulation

Suppose a browser sends a request.

```text
Application:
HTTP data

Transport:
TCP header + HTTP data

Internet:
IP header + TCP segment

Link:
Ethernet header/trailer + IP packet

Physical:
signals
```

At the receiver:

```text
signals
 → Ethernet frame
 → IP packet
 → TCP segment
 → HTTP data
```

## Why headers exist

Headers carry control information.

Examples:

- TCP: ports, sequence numbers, flags
- IP: source/destination addresses, TTL/hop limit
- Ethernet: source/destination MAC

## Exercise

Draw a packet leaving your laptop for a website. Label every address and identifier you know.

Then ask which fields can change at each router hop.
