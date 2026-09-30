# 20 — SSH and Remote Access

SSH provides secure remote administration and tunneling capabilities.

Common components:

```text
TCP connection
SSH protocol negotiation
key exchange
server authentication
user authentication
encrypted session
```

## Key authentication

Understand:

- private key
- public key
- authorized keys
- host keys
- known_hosts

## Security

Good administrative practice includes:

- strong authentication
- key management
- least privilege
- limiting management exposure
- logging
- patching
- disabling unnecessary access

## Lab

Build two local VMs.

Capture the connection.

You should be able to point to:

```text
TCP handshake
SSH identification/negotiation
encrypted payload
connection close
```

You should also be able to explain why the packet capture cannot simply display your terminal commands as plaintext.
