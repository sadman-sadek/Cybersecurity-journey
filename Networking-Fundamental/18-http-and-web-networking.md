# 18 — HTTP and Web Networking

## HTTP request

Conceptually:

```text
GET /index.html HTTP/1.1
Host: example.com
User-Agent: ...
```

## HTTP response

```text
HTTP/1.1 200 OK
Content-Type: text/html
Content-Length: ...
```

## Status classes

```text
1xx informational
2xx success
3xx redirection
4xx client-side error
5xx server-side error
```

Know common codes:

```text
200
201
204
301
302
304
400
401
403
404
429
500
502
503
```

## HTTP/1.1 vs HTTP/2 vs HTTP/3

Understand conceptually:

- HTTP/1.1 commonly uses one TCP connection with sequential/request concurrency features
- HTTP/2 multiplexes streams over a connection and uses binary framing
- HTTP/3 uses QUIC over UDP

## Security

Study:

- cookies
- sessions
- headers
- proxies
- reverse proxies
- authentication
- TLS
- request smuggling concept
- SSRF concept
- web reconnaissance from network evidence

Always separate **network-layer behavior** from **application-layer vulnerabilities**.
