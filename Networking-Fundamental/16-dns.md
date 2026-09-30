# 16 — DNS

DNS translates names into resource records.

Example:

```text
www.example.com
        ↓
A / AAAA record
        ↓
IP address
```

## Resolution chain

A simplified recursive resolution:

```text
Client
  ↓
Recursive resolver
  ↓
Root
  ↓
TLD
  ↓
Authoritative server
  ↓
Answer
```

Caching changes the exact path.

## Important record types

Know:

- A
- AAAA
- CNAME
- MX
- NS
- TXT
- PTR
- SOA

## Commands

Linux/macOS:

```bash
dig example.com
dig A example.com
dig AAAA example.com
dig MX example.com
dig +trace example.com
```

Windows:

```powershell
nslookup example.com
```

## Security

Understand:

- cache poisoning
- DNS spoofing
- DNS tunneling
- malicious domains
- fast-flux concepts
- DoH/DoT visibility tradeoffs
- DNS logging

## Packet exercise

Capture one DNS query and identify:

```text
transaction ID
flags
question
answer
TTL
source/destination
transport
```
