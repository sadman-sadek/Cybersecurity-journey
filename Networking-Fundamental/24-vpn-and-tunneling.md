# 24 — VPN and Tunneling

A tunnel carries one traffic context through another.

Conceptually:

```text
Original packet
      ↓
Encapsulation/encryption
      ↓
Tunnel
      ↓
Decapsulation
      ↓
Original packet
```

## VPN categories

Study:

- site-to-site VPN
- remote-access VPN
- IPsec
- TLS-based VPNs
- WireGuard concepts
- split tunneling
- full tunneling

## Security questions

A VPN does not magically make endpoints safe.

Ask:

- Who can connect?
- How are they authenticated?
- What networks can they reach?
- Is traffic logged?
- Is split tunneling allowed?
- What happens when the tunnel drops?

## Lab

Build two isolated networks connected by a VPN.

Verify:

```text
route before VPN
route after VPN
packet path
encryption boundary
access policy
```
