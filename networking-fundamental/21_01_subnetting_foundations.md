# Subnetting — The Skill You Must Own

Subnetting divides an IP address space into smaller networks.

## Why subnet?

- reduce broadcast scope
- organize networks
- use addresses efficiently
- enforce segmentation
- support routing design

## Powers of two

Memorize:

```text
2^0  = 1
2^1  = 2
2^2  = 4
2^3  = 8
2^4  = 16
2^5  = 32
2^6  = 64
2^7  = 128
2^8  = 256
```

## Example

`192.168.1.0/26`

A /26 has:

```text
32 - 26 = 6 host bits
2^6 = 64 total addresses
```

Traditional usable host count:

```text
64 - 2 = 62
```

Block size:

```text
256 - 192 = 64
```

Subnets in the last octet:

```text
0–63
64–127
128–191
192–255
```

For `192.168.1.70/26`:

- network: `192.168.1.64`
- broadcast: `192.168.1.127`
- usable range: `192.168.1.65–192.168.1.126`
