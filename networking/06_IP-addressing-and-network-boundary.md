# Part 3 --- IP Addressing, Subnetting, IPv6, MAC and Network Domains

# 1. IPv4 fundamentals

IPv4 uses **32-bit addresses**.

They are normally written as four decimal octets:

`192.168.10.25`

Each octet = 8 bits.

Maximum value per octet = **255**.

------------------------------------------------------------------------

# 2. IPv4 address structure

An IPv4 address contains:

-   Network portion
-   Host portion

The subnet mask/prefix determines where the boundary is.

Example:

`192.168.1.25/24`

`/24` means:

-   24 network bits
-   8 host bits

A `/24` IPv4 subnet contains:

**2\^8 = 256 total addresses**

Traditional usable-host calculation for a normal subnet:

**256 − 2 = 254 usable host addresses**

The two traditionally excluded addresses are: - Network address -
Broadcast address

> Modern special-purpose addressing can have different rules, so always
> consider the context.

------------------------------------------------------------------------

# 3. IPv4 private address ranges

The major RFC 1918 private ranges are:

  Range                            CIDR
  -------------------------------- ----------------
  10.0.0.0 -- 10.255.255.255       10.0.0.0/8
  172.16.0.0 -- 172.31.255.255     172.16.0.0/12
  192.168.0.0 -- 192.168.255.255   192.168.0.0/16

Private addresses are not globally routed on the public Internet.

NAT is commonly used to translate private addresses to public addresses.

------------------------------------------------------------------------

# 4. IPv4 address classes

Classful addressing is historical but still important for understanding
older networking.

  Class     First octet Default mask
  ------- ------------- -----------------------
  A              1--126 /8
  B            128--191 /16
  C            192--223 /24
  D            224--239 Multicast
  E            240--255 Experimental/reserved

### Important

Modern networks use **CIDR/classless addressing**, not traditional
classful addressing.

------------------------------------------------------------------------

# 5. Subnetting

Subnetting divides a larger network into smaller logical networks.

### Why subnet?

-   Reduce broadcast scope
-   Organize departments/sites
-   Improve address utilization
-   Apply security policies
-   Simplify routing

------------------------------------------------------------------------

# 6. Subnetting mechanism

Suppose:

`192.168.1.0/24`

You need 4 equal subnets.

Borrow 2 host bits:

`/24 → /26`

Because:

**2\^2 = 4 subnets**

Each /26 has:

**2\^(32−26) = 64 addresses**

Traditionally:

**64 − 2 = 62 usable host addresses**

The four ranges are:

-   192.168.1.0/26
-   192.168.1.64/26
-   192.168.1.128/26
-   192.168.1.192/26

### Fast subnetting rule

For a prefix `/n`:

**Host bits = 32 − n**

**Total addresses = 2\^(host bits)**

------------------------------------------------------------------------

# 7. CIDR --- Classless Inter-Domain Routing

CIDR writes the network prefix using slash notation.

Examples:

-   `/8`
-   `/16`
-   `/24`
-   `/30`

### Why CIDR?

It allows flexible network sizes instead of forcing Class A/B/C
boundaries.

### CIDR and routing

Routers use the prefix length to determine how much of the address
identifies the network.

------------------------------------------------------------------------

# 8. Route summarization / aggregation

Multiple contiguous routes can sometimes be represented by one larger
summary prefix.

Example:

`192.168.0.0/24` `192.168.1.0/24` `192.168.2.0/24` `192.168.3.0/24`

can be summarized as:

`192.168.0.0/22`

when the address blocks align correctly.

### Benefits

-   Smaller routing tables
-   Fewer routing updates
-   Simpler network design

### Caution

The networks must fit the summary boundary correctly.

------------------------------------------------------------------------

# 9. IPv6 fundamentals

IPv6 uses **128-bit addresses**.

Example:

`2001:db8:1234:5678:0000:0000:0000:0001`

IPv6 uses hexadecimal notation.

There are 8 groups called hextets.

Each hextet represents 16 bits.

------------------------------------------------------------------------

# 10. IPv6 compression rules

Leading zeros in a hextet can be removed.

`2001:0db8:0000:0000:0000:0000:0000:0001`

becomes:

`2001:db8::1`

### Double-colon rule

`::` can represent one or more consecutive groups of zeros.

It may appear **only once** in an IPv6 address.

------------------------------------------------------------------------

# 11. Important IPv6 address types

## Global unicast

Globally routable IPv6 addresses.

Commonly within:

`2000::/3`

## Link-local

Used for communication on the local link.

Prefix:

`FE80::/10`

Every IPv6-enabled interface normally has a link-local address.

## Unique local address

Private-like IPv6 addressing.

Prefix:

`FC00::/7`

In practice, locally assigned ULAs commonly use `FD00::/8`.

## Multicast

One-to-many communication.

Prefix:

`FF00::/8`

## Anycast

The same address is assigned to multiple interfaces; traffic is
delivered to the nearest/appropriate instance according to routing.

------------------------------------------------------------------------

# 12. IPv6 and broadcast

IPv6 does **not use broadcast** in the IPv4 sense.

It uses: - Unicast - Multicast - Anycast

Neighbor Discovery uses ICMPv6 multicast rather than ARP broadcasts.

------------------------------------------------------------------------

# 13. MAC addresses

A MAC address is a Layer 2 hardware/interface identifier used by
Ethernet and other link-layer technologies.

A traditional Ethernet MAC address is **48 bits**.

Example:

`00:1A:2B:3C:4D:5E`

### MAC vs IP

  MAC                   IP
  --------------------- ----------------------------
  Layer 2               Layer 3
  Local-link delivery   Logical network addressing
  Ethernet frame        IP packet
  Used by switches      Used by routers

### Important

A MAC address is not a substitute for an IP address.

------------------------------------------------------------------------

# 14. Collision domains

A **collision domain** is a portion of a network where devices could
potentially contend for the same shared transmission medium.

### Switch behavior

Each switch port normally creates a separate collision domain.

Modern full-duplex Ethernet eliminates normal Ethernet collisions on
that link.

### Hub behavior

A hub creates one shared collision domain.

------------------------------------------------------------------------

# 15. Broadcast domains

A **broadcast domain** is the set of devices that receive a Layer 2
broadcast.

### Routers

Routers normally separate broadcast domains.

### VLANs

Each VLAN is normally a separate Layer 2 broadcast domain.

### Key distinction

-   **Switch port:** normally separates collision domains.
-   **Router/VLAN boundary:** separates broadcast domains.

------------------------------------------------------------------------

# 16. Network transmission types

## Unicast

One sender → one receiver.

## Broadcast

One sender → all hosts in the local broadcast domain.

## Multicast

One sender → subscribed group of receivers.

## Anycast

One address → one selected member of a group, generally the nearest
according to routing.

------------------------------------------------------------------------

# 17. Quick recall

-   IPv4 = **32 bits**
-   IPv6 = **128 bits**
-   Ethernet MAC = commonly **48 bits**
-   `/24` = 24 network bits + 8 host bits
-   CIDR = classless prefix notation
-   Subnetting = divide networks
-   Summarization = combine routes
-   Collision domain ≠ broadcast domain
-   IPv6 has no traditional broadcast
-   Unicast = one-to-one
-   Broadcast = one-to-all on the local broadcast domain
-   Multicast = one-to-group
-   Anycast = one-to-nearest/selected instance

## Exam traps

-   Do not call a MAC address a Layer 3 address.
-   Do not say switches normally separate broadcast domains; VLAN
    configuration is what creates Layer 2 broadcast-domain boundaries.
-   Do not use classful thinking when calculating modern CIDR networks.
-   Remember IPv6 is 128-bit, not 64-bit.
