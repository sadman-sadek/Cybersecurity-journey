# 28 — Troubleshooting

## The golden rule

Do not change five things at once.

Change one thing, test, record.

## Layered troubleshooting

```text
Physical
↓
Link
↓
IP configuration
↓
Neighbor discovery
↓
Routing
↓
Firewall
↓
Transport
↓
Application
```

## Linux commands

```bash
ip addr
ip link
ip route
ip neigh
ss -lntup
ping
traceroute
dig
curl
```

## Windows

```powershell
ipconfig /all
Get-NetIPConfiguration
Get-NetRoute
Get-NetNeighbor
Get-NetTCPConnection
Test-NetConnection
Resolve-DnsName
tracert
```

## Example

Symptom:

```text
Browser cannot reach website
```

Do not immediately blame the browser.

Test:

```text
1. Link?
2. IP?
3. Gateway?
4. DNS?
5. TCP 443?
6. TLS?
7. HTTP?
```

## Build a troubleshooting tree

For each failure, document:

```text
Symptom
Possible causes
Test
Observation
Conclusion
Fix
Verification
```
