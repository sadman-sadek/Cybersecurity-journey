# Packet, Frame, Segment and Payload

People often casually call all network data a "packet", but different layers have different terms.

Typical TCP/IP encapsulation:

```text
Application data
      ↓
TCP segment / UDP datagram
      ↓
IP packet
      ↓
Ethernet frame
      ↓
Bits/signals
```

## Why multiple names?

Each layer adds information needed by its own job.

Example:

```text
Ethernet Header
    IP Header
        TCP Header
            Application Data
```

At the destination, this is reversed:

```text
Bits
 → Frame
 → Packet
 → Segment
 → Application data
```

## Key insight

A router generally removes the incoming Layer-2 frame and creates a new Layer-2 frame for the next link.

The IP packet is forwarded through the routed path, although its Layer-2 wrapping changes hop by hop.
