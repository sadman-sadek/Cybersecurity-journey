# 35 — Python Networking

Python becomes powerful when networking fundamentals are already strong.

## TCP client

```python
import socket

with socket.create_connection(("example.com", 443), timeout=5) as s:
    print(s.getpeername())
```

Understand every part:

- DNS resolution
- socket creation
- TCP connection
- local ephemeral port
- remote port
- connection close

## UDP example

```python
import socket

sock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
sock.settimeout(2)
sock.sendto(b"hello", ("127.0.0.1", 9999))
```

## Build progressively

1. TCP client
2. TCP server
3. UDP client/server
4. DNS lookup tool
5. port-state checker for your lab
6. connection logger
7. packet metadata analyzer using a pcap library
8. simple network inventory tool

## Rule

Do not copy a scanner and call it mastery.

Write a small tool, then explain:

```text
socket
address
port
timeout
protocol
error
result
```
