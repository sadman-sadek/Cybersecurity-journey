# 02 — Networking Mindset

Networking becomes easier when you stop seeing it as hundreds of protocols.

Think in five questions:

1. **Who is talking?**
2. **Where are they?**
3. **How do they find each other?**
4. **How does the data travel?**
5. **What state/security controls exist along the way?**

## The layered picture

A web request can be imagined as:

```text
Application:  HTTP request
Transport:    TCP segment
Network:      IP packet
Data Link:    Ethernet frame
Physical:     electrical/radio/optical signals
```

Each layer wraps the layer above:

```text
[Ethernet
   [IP
      [TCP
         [HTTP
            DATA
         ]
      ]
   ]
]
```

## Cybersecurity translation

A defender asks:

- Which identity is represented by each layer?
- Can that identity be spoofed?
- Can metadata reveal sensitive information?
- Where can traffic be filtered?
- Where can traffic be observed?
- What state can be abused?
- What happens if a component lies?

## One powerful habit

Whenever you see an address, classify it:

```text
MAC?        Layer 2
IPv4/IPv6?  Layer 3
Port?       Layer 4
URL/name?   Application
```

Then ask:

**What happens to this value at the next hop?**
