# Ports and Sockets

A port identifies a transport-layer service endpoint.

Example:

```text
192.168.1.10:51522
```

A server may listen on:

```text
192.168.1.20:443
```

A TCP connection is commonly identified by a 4-tuple:

```text
source IP
source port
destination IP
destination port
```

The protocol also matters in practical identification.

## Common ports to recognize

| Service | Typical port |
|---|---:|
| HTTP | 80/TCP |
| HTTPS | 443/TCP |
| SSH | 22/TCP |
| DNS | 53/UDP and 53/TCP |
| DHCP server/client | 67/68 UDP |
| NTP | 123/UDP |
| SMTP submission | 587/TCP |
| IMAP | 143/TCP |
| IMAPS | 993/TCP |
| LDAP | 389/TCP/UDP |
| LDAPS | 636/TCP |
| SNMP | 161/UDP |
| SNMP traps | 162/UDP |

Ports are conventions, not magical guarantees. A service can sometimes listen on a different port.
