# Default Gateway

A host compares the destination IP with its own network information.

If the destination is on the same local subnet, the host can deliver locally.

If it is on another IP network, the host sends the packet to its **default gateway**.

Example:

```text
PC:       192.168.1.10/24
Gateway:  192.168.1.1
Server:   192.168.2.20
```

The server is outside `192.168.1.0/24`, so the PC sends the frame to the gateway's MAC address.

## Key distinction

The gateway is not "the Internet".

It is the local router/interface that provides a next-hop path for destinations not considered local.
