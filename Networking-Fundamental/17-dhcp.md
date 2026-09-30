# 17 — DHCP

DHCP dynamically provides network configuration.

Common sequence:

```text
Discover
Offer
Request
ACK
```

Often remembered as:

**DORA**

## What can DHCP provide?

Depending on configuration:

- IP address
- subnet mask/prefix
- default gateway
- DNS servers
- lease information
- other options

## Security relevance

Rogue DHCP can redirect clients toward malicious infrastructure.

Defensive concepts:

- DHCP snooping
- trusted/untrusted switch ports
- monitoring unexpected DHCP servers
- validating gateway/DNS configuration

## Lab

Capture a lease process in an isolated network.

Write down:

```text
client MAC
offered IP
server IP
gateway
DNS
lease information
```

Then explain what would happen if the client accepted configuration from an unauthorized server.
