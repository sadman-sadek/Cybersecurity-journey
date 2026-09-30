# 19 — TLS and HTTPS

TLS provides cryptographic protection for application traffic.

Think in three properties:

```text
Confidentiality
Integrity
Authentication (when certificate validation succeeds)
```

## High-level handshake

Modern TLS negotiation involves:

- protocol version
- cipher suite negotiation
- key exchange
- authentication/certificate validation
- establishment of symmetric session keys

Do not memorize a fictional fixed sequence. TLS versions differ.

## Certificate questions

A client may check:

- hostname
- validity period
- trust chain
- key usage
- certificate signature
- revocation/status mechanisms depending on implementation

## What HTTPS does not guarantee

HTTPS does not automatically mean:

- the site is legitimate
- the server is harmless
- the content is safe
- the endpoint is uncompromised

It protects the connection according to the negotiated security properties.

## Lab

Use:

```bash
curl -v https://example.com
```

Then inspect a capture.

Identify what is visible despite encryption:

- IP addresses
- ports
- packet sizes/timing
- TLS handshake metadata
- encrypted application payload

This is critical for network monitoring.
