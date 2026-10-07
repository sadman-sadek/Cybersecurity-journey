# Subnet Masks and CIDR

CIDR notation:

```text
192.168.10.0/24
```

`/24` means 24 network bits and 8 host bits.

Equivalent mask:

```text
255.255.255.0
```

## Prefix intuition

```text
/8   = 24 host bits
/16  = 16 host bits
/24  = 8 host bits
/30  = 2 host bits
```

For ordinary IPv4 subnet calculations:

```text
host addresses = 2^(host bits) - 2
```

The subtraction accounts for the network and broadcast addresses in traditional subnetting.

Be aware that special cases exist, including point-to-point designs and modern IPv4 operational conventions.
