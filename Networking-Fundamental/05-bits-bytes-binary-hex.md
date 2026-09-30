# 05 — Bits, Bytes, Binary and Hex

## Why cybersecurity people need this

You will encounter:

- IPv4 masks
- IPv6
- MAC addresses
- packet bytes
- flags
- protocol fields
- hashes
- offsets

## Binary

One byte:

```text
128 64 32 16 8 4 2 1
 1  0  1  0 0 1 0 0

= 128 + 32 + 4
= 164
```

## Hex

One hex digit = 4 bits.

```text
0000 = 0
0001 = 1
...
1001 = 9
1010 = A
...
1111 = F
```

One byte = two hex digits:

```text
1111 0000 = F0
```

## Practice

Convert without a calculator:

```text
10 → binary
31 → binary
64 → binary
127 → binary
128 → binary
192 → binary
224 → binary
255 → binary
```

Then reverse the process.

## Cyber exercise

Take a packet capture and locate a recognizable value such as an IPv4 address. Identify:

- byte offset
- decimal representation
- hexadecimal representation
- binary representation
