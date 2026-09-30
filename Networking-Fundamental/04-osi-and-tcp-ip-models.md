# 04 — OSI and TCP/IP Models

## OSI layers

```text
7 Application
6 Presentation
5 Session
4 Transport
3 Network
2 Data Link
1 Physical
```

## Practical TCP/IP model

```text
Application
Transport
Internet
Link
```

## Why layers matter in cybersecurity

A failure at one layer can look like another layer's failure.

Example:

```text
DNS name fails
      ↓
Is DNS actually broken?
      ↓
Maybe IP connectivity is broken.
      ↓
Maybe ARP is broken.
      ↓
Maybe NIC/link is down.
```

## Encapsulation

```text
Application data
      ↓
TCP header + data
      ↓
IP header + TCP segment
      ↓
Ethernet header + IP packet + FCS
```

At each router:

- the Layer-2 frame is normally replaced
- the Layer-3 source/destination generally remain end-to-end
- TTL/Hop Limit changes
- checksums may change depending on protocol/header
