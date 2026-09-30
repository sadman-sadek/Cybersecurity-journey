# 33 — Linux Networking

## Essential commands

```bash
ip addr
ip link
ip route
ip neigh
ss -lntup
resolvectl status
hostname -I
```

## Inspect interfaces

```bash
ip link
ip addr
```

Understand:

- interface state
- MAC address
- IPv4/IPv6 addresses
- prefix
- scope

## Routes

```bash
ip route
ip -6 route
```

## Sockets

```bash
ss -lntup
```

Learn to map:

```text
process → socket → port → packet
```

## Network namespaces

Linux namespaces are an excellent learning tool.

Conceptually:

```text
namespace A       namespace B
  eth0               eth0
    \                 /
     virtual Ethernet
```

Build two isolated namespaces and connect them.

This teaches:

- interfaces
- routing
- ARP
- isolation
- namespaces
