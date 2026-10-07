# Troubleshooting Scenarios

## Scenario 1

You can ping `8.8.8.8` but cannot open `google.com`.

Likely investigation area: DNS.

## Scenario 2

You can reach local devices but not remote networks.

Investigate:

- default gateway
- routing
- NAT
- upstream connectivity

## Scenario 3

IP address works, TCP port does not.

Investigate:

- service listening state
- firewall
- ACL
- route
- port mismatch

## Scenario 4

Only one VLAN has problems.

Investigate:

- VLAN membership
- trunking
- SVI/gateway
- ACL
- DHCP scope

## Scenario 5

Wi-Fi is connected but slow.

Investigate:

- signal
- interference
- channel utilization
- negotiated rate
- packet loss
- upstream bandwidth
- application behavior

The goal is not to guess the cause. The goal is to produce evidence.
