# Subnetting Cheat Sheet

```text
Prefix   Host bits   Total addresses   Traditional usable
/24      8           256               254
/25      7           128               126
/26      6           64                62
/27      5           32                30
/28      4           16                14
/29      3           8                 6
/30      2           4                 2
```

Formula:

```text
host bits = 32 - prefix
total = 2^(host bits)
traditional usable = total - 2
```

Block size in the interesting octet:

```text
256 - mask value
```
