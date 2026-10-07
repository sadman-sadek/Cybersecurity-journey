# MAC Addresses

Ethernet interfaces use MAC addresses for local Layer-2 delivery.

A MAC address is typically represented as six hexadecimal octets, e.g.:

```text
00:11:22:33:44:55
```

## Important distinction

MAC addressing is primarily about **local link delivery**.

IP addressing is about **logical network-layer communication**.

A host can keep its IP address while the Ethernet destination MAC changes at every routed hop.

## Special destinations

- Broadcast: all hosts on the local broadcast domain
- Unicast: one destination
- Multicast: a group of destinations

## Security note

MAC addresses are not reliable proof of identity. They can often be changed/spoofed in software.
