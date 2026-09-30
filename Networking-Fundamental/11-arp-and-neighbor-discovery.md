# 11 — ARP and IPv6 Neighbor Discovery

## ARP

IPv4 hosts need to map:

```text
IPv4 address → MAC address
```

Example:

```text
Who has 192.168.1.1?
Tell 192.168.1.10
```

The request is typically broadcast at Layer 2.

The response can be unicast.

## ARP cache

Your machine remembers mappings temporarily.

Linux:

```bash
ip neigh
```

Windows:

```powershell
arp -a
```

## Security

ARP is not authenticated.

That creates opportunities for:

- spoofing
- cache poisoning
- traffic interception

In an authorized lab, observe normal ARP first. Do not jump straight to attack tooling.

## IPv6

IPv6 replaces ARP with Neighbor Discovery mechanisms using ICMPv6.

Useful command:

```bash
ip -6 neigh
```

## Lab

Capture traffic while a host contacts a new local IPv4 address.

Predict:

1. ARP request
2. ARP reply
3. actual IP traffic

Then clear the neighbor cache and repeat.
