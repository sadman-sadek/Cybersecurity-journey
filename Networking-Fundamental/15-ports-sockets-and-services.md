# 15 — Ports, Sockets and Services

## Port

A transport-layer port identifies an application endpoint within a host.

Example:

```text
10.0.0.5:443
```

means:

```text
IP = 10.0.0.5
Port = 443
```

## Socket

Conceptually:

```text
protocol + local IP + local port + remote IP + remote port
```

## Listening service

Linux:

```bash
ss -lntup
```

Windows:

```powershell
Get-NetTCPConnection -State Listen
```

## Important idea

A port number does not prove the service.

Port 443 often means HTTPS, but an administrator can run something else there.

Security tools therefore inspect behavior, banners, protocol patterns and application-layer evidence.

## Lab

1. Start a local HTTP server.
2. Find its listening socket.
3. Connect with a browser/curl.
4. Capture traffic.
5. Map the socket to packets.
