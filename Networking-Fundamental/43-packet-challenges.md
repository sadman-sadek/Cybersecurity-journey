# 43 — Packet Challenges

These are deliberately investigation-oriented.

## Challenge 1 — "The website is down"

Evidence:

```text
DNS succeeds.
TCP SYN leaves.
No SYN-ACK returns.
```

Questions:

- Where is the likely failure domain?
- What additional evidence do you need?
- Could the server be down?
- Could a firewall be dropping traffic?
- Could the return path be broken?

## Challenge 2 — "DNS is slow"

Evidence:

```text
Queries leave immediately.
Responses arrive after long delays.
```

Investigate:

- resolver
- packet loss
- upstream path
- TCP fallback
- DNS server load

## Challenge 3 — "Only one VLAN fails"

Investigate:

- VLAN assignment
- trunk
- gateway
- route
- ACL
- DHCP
- firewall

## Challenge 4 — "Connections reset"

Investigate:

```text
Who sends RST?
When?
After what packet?
Is it consistent?
```

## Challenge 5 — "Huge outbound traffic"

Do not immediately declare exfiltration.

Investigate:

- process
- destination
- protocol
- baseline
- expected backup/update behavior
- timing
- data volume

## Challenge 6 — "Port scan or application?"

Compare:

```text
many SYNs to many ports
```

against:

```text
normal application connection patterns
```

Learn why context matters.
