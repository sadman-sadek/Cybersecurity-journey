# Networking in One Page

```text
APPLICATION
HTTP DNS SSH DHCP NTP
        │
TRANSPORT
TCP / UDP
ports • sessions • reliability
        │
INTERNET
IPv4 / IPv6
addresses • routing • TTL/hop limit
        │
LINK
Ethernet / Wi-Fi
MAC • frames • switching • VLANs
        │
PHYSICAL
copper • fiber • radio
```

## Local delivery

```text
IP destination local?
 ├─ YES → resolve destination MAC → send frame
 └─ NO  → resolve gateway MAC → send frame to router
```

## Router

```text
receive frame
→ inspect IP packet
→ route lookup
→ decrement TTL/hop limit
→ build next-hop Layer-2 frame
→ transmit
```

## Troubleshooting

```text
Physical
→ Link
→ IP
→ Route
→ DNS
→ Transport
→ TLS/Application
```

## The master mental model

**Address tells you where.  
Routing tells you which path.  
MAC/link tells you how to reach the next local hop.  
Ports identify transport endpoints.  
Protocols define what the communication means.**
