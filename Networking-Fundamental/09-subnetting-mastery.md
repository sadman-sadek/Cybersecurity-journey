# 09 — Subnetting Mastery

Subnetting is a foundational cybersecurity skill.

## The only formula you need first

For IPv4 prefix length `/n`:

```text
host bits = 32 - n
usable host count is commonly 2^(host bits) - 2
```

There are important exceptions and modern conventions, so understand the reasoning rather than blindly applying the formula.

## Example

`192.168.10.0/26`

```text
/26 → 6 host bits
2^6 = 64 addresses
```

Typical range:

```text
Network:   192.168.10.0
Hosts:     192.168.10.1–62
Broadcast: 192.168.10.63
```

## Fast block-size method

For `/26`:

```text
256 - 192 = 64
```

Networks increment by 64:

```text
.0
.64
.128
.192
```

## Practice ladder

Solve these without tools:

1. `10.10.10.0/24`
2. `10.10.10.0/25`
3. `10.10.10.0/26`
4. `10.10.10.0/27`
5. `172.16.20.64/28`
6. `192.168.50.128/29`

For each, identify:

```text
network
first usable
last usable
broadcast
total addresses
host addresses
```

## Cybersecurity use cases

Subnetting appears in:

- firewall rules
- ACLs
- network segmentation
- cloud security groups
- route tables
- incident-response scoping
- log filtering
- asset inventory
