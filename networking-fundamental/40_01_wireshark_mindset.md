# Wireshark Mindset

Packet analysis turns networking from theory into observable evidence.

## First capture

Capture traffic while you:

1. ping a local host
2. ping a remote host
3. resolve a DNS name
4. open a website
5. establish an SSH connection

## Questions

For a DNS query:

- source IP?
- destination IP?
- UDP/TCP?
- source port?
- destination port?
- query name?
- response?
- timing?

For TCP:

- SYN?
- SYN-ACK?
- ACK?
- sequence numbers?
- retransmissions?
- FIN/RST?

For Ethernet:

- source MAC?
- destination MAC?
- EtherType?

For IP:

- source?
- destination?
- TTL?
- protocol?

## Golden rule

Never stare at packets randomly.

Have a question first.
