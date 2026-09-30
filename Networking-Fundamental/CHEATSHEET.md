# Networking Command Cheatsheet

## Linux

```bash
ip addr
ip link
ip route
ip neigh
ss -lntup
ping <host>
traceroute <host>
dig <domain>
curl -v https://example.com
sudo tcpdump -i any
```

## Windows

```powershell
ipconfig /all
Get-NetIPConfiguration
Get-NetRoute
Get-NetNeighbor
Get-NetTCPConnection
Test-NetConnection <host> -Port 443
Resolve-DnsName <domain>
tracert <host>
```

## Packet filters

```text
arp
icmp
dns
tcp
udp
http
tls
ssh
ip.addr == X.X.X.X
tcp.port == 443
udp.port == 53
tcp.flags.syn == 1
tcp.flags.reset == 1
```

## Core mental map

```text
MAC       → local Layer 2 delivery
IP        → Layer 3 addressing/routing
Port      → Layer 4 application endpoint
DNS       → names ↔ records
ARP       → IPv4 neighbor mapping
TCP       → reliable byte stream
UDP       → lightweight datagrams
ICMP      → network control/error
DHCP      → dynamic configuration
TLS       → cryptographic transport protection
HTTP      → web application protocol
Firewall  → traffic policy
NAT       → address translation
VPN       → protected/tunneled connectivity
```
