# 2 — OSI, TCP/IP and Encapsulation

## OSI
| Layer | Name | Examples |
|---|---|---|
| 7 | Application | HTTP, DNS, SSH |
| 6 | Presentation | Encoding/encryption concepts |
| 5 | Session | Sessions |
| 4 | Transport | TCP, UDP |
| 3 | Network | IPv4, IPv6, routing |
| 2 | Data Link | Ethernet, MAC, VLAN |
| 1 | Physical | Copper, fiber, radio |

Memory: **Please Do Not Throw Sausage Pizza Away** (7→1).

## TCP/IP model
- Application
- Transport
- Internet
- Network Access/Link

## Encapsulation
Application data → TCP/UDP segment/datagram → IP packet → Ethernet/Wi-Fi frame → bits.
At the destination the process is reversed.

## PDU
- L1: bits
- L2: frame
- L3: packet
- L4: segment (TCP) / datagram (UDP)

## What changes at a router?
The Layer 2 frame is normally removed and a new Layer 2 frame is created for the next link. The Layer 3 destination remains the same end-to-end unless a mechanism such as NAT changes addressing.

## Troubleshooting value
If a problem is physical, fixing DNS will not help. If the IP route is broken, application settings may be irrelevant. Always connect symptoms to layers.
