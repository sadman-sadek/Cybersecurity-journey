# 13 — TCP

TCP provides reliable, ordered, connection-oriented byte-stream transport.

## Three-way handshake

```text
Client                 Server
  | ---- SYN ----------> |
  | <--- SYN-ACK ------- |
  | ---- ACK ----------> |
```

## Sequence and acknowledgment numbers

Think:

```text
SEQ = "Here is byte position X."
ACK = "I expect byte position Y next."
```

TCP does not preserve application message boundaries. It provides a byte stream.

## Flags

Know the purpose of:

- SYN
- ACK
- FIN
- RST
- PSH
- URG

Also understand modern ECN-related flags at a conceptual level.

## TCP state

Common states:

```text
LISTEN
SYN-SENT
SYN-RECEIVED
ESTABLISHED
FIN-WAIT
TIME-WAIT
CLOSE-WAIT
```

## Security

Learn to recognize:

- SYN floods
- reset behavior
- port scanning patterns
- connection exhaustion
- abnormal retransmissions
- asymmetric traffic

## Lab

Start a local TCP server.

Capture:

1. SYN
2. SYN-ACK
3. ACK
4. application data
5. connection close

Then explain every sequence/acknowledgment number you can see.
