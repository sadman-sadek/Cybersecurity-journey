# 06 — Ethernet and MAC

## Mental model

Ethernet answers:

**Who should receive this frame on this local Layer-2 network?**

A MAC address is typically 48 bits.

Example:

```text
00:11:22:33:44:55
```

## Frame concept

```text
+------------------+
| Destination MAC  |
+------------------+
| Source MAC       |
+------------------+
| EtherType/Length |
+------------------+
| Payload          |
+------------------+
| FCS              |
+------------------+
```

## Unicast, broadcast, multicast

Broadcast:

```text
ff:ff:ff:ff:ff:ff
```

A common IPv4 ARP request uses broadcast Ethernet delivery because the sender does not yet know the destination MAC.

## Switch learning

Imagine:

```text
A ----\
       Switch ---- B
C ----/
```

When A sends a frame, the switch learns:

```text
source MAC A → incoming port
```

Then it can forward future frames more selectively.

## Security relevance

Understand:

- MAC spoofing
- CAM table behavior
- VLAN boundaries
- broadcast exposure
- rogue devices
- Layer-2 monitoring

Do not memorize attacks before understanding normal switching.
