# Subnetting Drills

Do these without a calculator.

## Drill A

Find network, broadcast and usable range:

`192.168.10.77/27`

## Drill B

`10.20.33.200/20`

## Drill C

`172.16.100.14/30`

## Drill D

How many total addresses and traditional usable hosts are in `/25`, `/26`, `/27`, `/28`, `/29`, `/30`?

## Drill E — VLSM thinking

You have `192.168.50.0/24`.

Requirements:

- Network A: 100 hosts
- Network B: 50 hosts
- Network C: 25 hosts
- Network D: 10 hosts

Design subnets with minimal waste.

## Answers

### A

`/27` block size = 32.

`77` is in `64–95`.

- network: `192.168.10.64`
- broadcast: `192.168.10.95`
- hosts: `.65–.94`

### B

/20 has 12 host bits.

Block size in the third octet = 16.

100 falls in 96–111.

- network: `10.20.96.0`
- broadcast: `10.20.111.255`
- usable: `10.20.96.1–10.20.111.254`

### C

/30 block size = 4.

14 falls in 12–15.

- network: `172.16.100.12`
- broadcast: `172.16.100.15`
- usable: `.13–.14`

### D

| Prefix | Total | Traditional usable |
|---|---:|---:|
| /25 | 128 | 126 |
| /26 | 64 | 62 |
| /27 | 32 | 30 |
| /28 | 16 | 14 |
| /29 | 8 | 6 |
| /30 | 4 | 2 |

### E

One valid VLSM design:

- 100 hosts → /25
- 50 hosts → /26
- 25 hosts → /27
- 10 hosts → /28

Allocate largest first to avoid fragmentation.
