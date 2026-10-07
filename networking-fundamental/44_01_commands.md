# Essential Networking Commands

## Windows

```powershell
ipconfig /all
ping 8.8.8.8
tracert example.com
arp -a
nslookup example.com
netstat -ano
```

PowerShell often provides richer alternatives such as:

```powershell
Get-NetIPConfiguration
Get-NetRoute
Test-NetConnection example.com -Port 443
```

## Linux

```bash
ip addr
ip route
ping 8.8.8.8
traceroute example.com
ip neigh
dig example.com
ss -tulpn
curl -I https://example.com
```

## Command philosophy

Do not memorize commands as spells.

Know what question each command answers.

Example:

```text
ip route
```

Question:

> What routes does this machine currently know?
