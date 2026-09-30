# 21 — NAT and Firewalls

## NAT

Network Address Translation changes address information as traffic crosses a device.

Common home setup:

```text
Private host
192.168.1.10:51514
        ↓
NAT gateway
        ↓
Public address:ephemeral-port
        ↓
Internet server
```

## Important distinction

NAT is not identical to a firewall.

NAT changes addressing.

A firewall enforces policy.

They often coexist.

## Stateful firewall

A stateful firewall tracks connection state.

Conceptually:

```text
NEW
ESTABLISHED
RELATED
```

Rules can use:

- source/destination IP
- ports
- protocol
- interface
- state
- direction

## Lab

Create a small Linux router/firewall VM.

Test:

```text
client → server
server → client
client → blocked port
```

Observe both allowed and denied traffic.

## Security reasoning

For every firewall rule ask:

```text
Who?
To where?
Using what protocol?
Which port?
In which direction?
Under what state?
Why is it needed?
What is the narrowest safe scope?
```
