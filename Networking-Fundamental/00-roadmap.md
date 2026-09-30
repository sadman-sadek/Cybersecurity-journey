# 00 — Roadmap: Beginner → Network Security Engineer

## The four levels

### Level 1 — Can describe it

You can answer:

- What is an IP address?
- What is a MAC address?
- What does a switch do?
- What does a router do?
- What is a port?
- What is TCP?

This is not enough.

### Level 2 — Can observe it

You can:

- capture traffic
- identify Ethernet/IP/TCP/UDP/DNS/HTTP fields
- explain a packet's journey
- use `ip`, `ss`, `ping`, `traceroute`, `dig`, `curl`, `tcpdump`

### Level 3 — Can build and break it

You can:

- create VLANs
- configure routes
- build a small DNS/DHCP environment
- create firewall rules
- troubleshoot broken connectivity
- reproduce protocol behavior in a lab

### Level 4 — Can reason about unfamiliar networks

You can look at:

```text
host → switch → router → firewall → NAT → Internet → server
```

and reason about:

- addressing
- route selection
- state
- trust boundaries
- protocol behavior
- failure modes
- detection opportunities

That is the level cybersecurity work demands.

## Mastery checklist

You should eventually be able to explain, without notes:

- Why a host ARPs before sending an IPv4 packet on a LAN.
- Why a router decrements TTL/hop limit.
- Why TCP needs sequence and acknowledgment numbers.
- Why a switch does not normally route between IP networks.
- Why DNS can use both UDP and TCP.
- Why HTTPS encrypts application data but does not make an endpoint trustworthy.
- Why NAT is not a complete security boundary.
- Why a firewall can allow TCP SYN while blocking a later packet.
- Why `ping` can fail while an application still works.
- Why two machines on the same subnet do not necessarily communicate.
- Why a route can exist but traffic can still fail.
- Why packet captures from different points show different source/destination addresses.

## The expert loop

For every new protocol:

1. What problem does it solve?
2. What does the sender know?
3. What does the receiver know?
4. What state is maintained?
5. What does the wire look like?
6. What can fail?
7. What can an attacker abuse?
8. What evidence would detection tools see?
9. How would you troubleshoot it?
10. Can you script or automate a useful part of it?
