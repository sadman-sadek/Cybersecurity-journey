# Static vs Dynamic Routing

## Static routing

A human/admin explicitly configures routes.

Advantages:

- predictable
- simple for small topologies
- no routing-protocol overhead

Disadvantages:

- manual
- harder to maintain at scale
- changes do not automatically propagate

## Dynamic routing

Routers exchange routing information using routing protocols.

Examples:

- OSPF
- EIGRP
- IS-IS
- BGP

Dynamic routing enables networks to adapt to topology changes.

## Key distinction

A routing protocol is not the same thing as IP forwarding.

The routing protocol helps a router learn routes.

The forwarding process uses the resulting information to move packets.
