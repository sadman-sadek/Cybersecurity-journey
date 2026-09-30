# 26 — Wireshark Playbook

## Filters worth learning

```text
arp
icmp
dns
tcp
udp
http
tls
ssh
ip.addr == 192.168.1.10
ip.src == 192.168.1.10
ip.dst == 8.8.8.8
tcp.port == 443
udp.port == 53
tcp.flags.syn == 1
tcp.flags.reset == 1
```

Use filters as hypotheses, not magic.

## Essential features

Learn to use:

- packet details
- packet bytes
- Follow TCP Stream
- Conversations
- Endpoints
- Protocol Hierarchy
- I/O graphs
- Expert information

## First 10 captures

Capture:

1. ARP
2. ping
3. DNS
4. DHCP
5. TCP handshake
6. HTTP
7. HTTPS
8. SSH
9. failed TCP connection
10. retransmission

For every capture write a one-paragraph explanation.

## Security workflow

When investigating suspicious traffic:

```text
Who initiated?
↓
What destination?
↓
Which protocol?
↓
Which port?
↓
What happened before?
↓
What happened after?
↓
Is behavior normal?
↓
What evidence supports the conclusion?
```
