# 34 — Windows Networking

## Core commands

```powershell
ipconfig /all
Get-NetIPConfiguration
Get-NetAdapter
Get-NetRoute
Get-NetNeighbor
Get-NetTCPConnection
Test-NetConnection
Resolve-DnsName
tracert
pathping
```

## Useful investigation

Find listening/active connections:

```powershell
Get-NetTCPConnection
```

Test a specific service:

```powershell
Test-NetConnection example.com -Port 443
```

Resolve DNS:

```powershell
Resolve-DnsName example.com
```

## Cybersecurity angle

Learn to correlate:

```text
Windows process
→ socket
→ remote IP
→ remote port
→ DNS name
→ firewall/log evidence
```

That correlation is extremely useful during incident response.
