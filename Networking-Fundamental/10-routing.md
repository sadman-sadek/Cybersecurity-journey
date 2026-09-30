# 10 — Routing

Routing answers:

**Which next hop/interface should receive this packet?**

## Routing table

Conceptual example:

```text
Destination       Next Hop       Interface
10.0.0.0/8        —              eth0
192.168.1.0/24    —              eth1
0.0.0.0/0         192.168.1.1     eth1
```

## Longest prefix match

If multiple routes match, the most specific prefix normally wins.

Example:

```text
10.0.0.0/8
10.10.0.0/16
10.10.10.0/24
```

Destination:

```text
10.10.10.42
```

The `/24` is the most specific match.

## Default route

```text
0.0.0.0/0
```

means "use this route when nothing more specific matches."

## Static vs dynamic routing

Static:

- manually configured
- predictable
- can be simple

Dynamic:

- routers exchange reachability information
- adapts to topology changes
- introduces protocol/state complexity

Study:

- RIP conceptually
- OSPF deeply
- BGP conceptually first, then deeply if your career requires it

## Troubleshooting chain

```text
Is interface up?
↓
Does host have an address?
↓
Is local neighbor reachable?
↓
Is route present?
↓
Is next hop reachable?
↓
Does return route exist?
↓
Is policy blocking it?
```
