# Routing Fundamentals

Routing is the process of deciding where an IP packet should go next.

A router has routes.

Conceptually:

```text
Destination prefix       Next hop/interface
10.10.0.0/16             Router A
192.168.20.0/24          Router B
0.0.0.0/0                ISP
```

## Longest Prefix Match

If multiple routes match a destination, the most specific matching prefix generally wins.

Example:

```text
10.0.0.0/8
10.20.0.0/16
10.20.30.0/24
```

Destination `10.20.30.50` matches all three.

The `/24` is the most specific.

## Default route

IPv4:

```text
0.0.0.0/0
```

IPv6:

```text
::/0
```

It matches destinations for which no more specific route exists.

## Routing table mindset

When troubleshooting:

1. What is the destination IP?
2. Which route matches?
3. What is the next hop?
4. Which interface is used?
5. Can the router reach the next hop?
6. Can the next router continue the journey?
