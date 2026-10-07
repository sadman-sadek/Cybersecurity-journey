# HTTP and HTTPS

HTTP is an application-layer protocol used for web communication.

Typical request:

```text
Client → HTTP request → Server
Client ← HTTP response ← Server
```

Important concepts:

- methods: GET, POST, PUT, DELETE, etc.
- status codes: 2xx, 3xx, 4xx, 5xx
- headers
- body
- cookies
- caching

## HTTPS

HTTPS is HTTP protected using TLS.

A simplified stack:

```text
HTTP
TLS
TCP
IP
Link
```

Modern HTTP/3 commonly uses QUIC over UDP rather than TCP.

## Troubleshooting example

If DNS resolves but HTTPS fails:

1. Can you reach the IP?
2. Is TCP/QUIC connectivity possible?
3. Is the server listening?
4. Is TLS negotiation successful?
5. Is the HTTP request valid?
6. Is an application-layer policy blocking it?
