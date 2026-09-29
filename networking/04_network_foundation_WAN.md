# Part 1 --- Networking Foundations and WAN Technologies

## 1. Network basics

A **computer network** is a group of devices connected so they can
exchange data and share resources.

### Common network components

-   **Host/end device:** PC, phone, server, printer, camera, IoT device.
-   **NIC:** Network Interface Card; connects a device to a network.
-   **Switch:** Connects devices inside a LAN and forwards Ethernet
    frames.
-   **Router:** Connects different IP networks and forwards packets
    between them.
-   **Access Point (AP):** Provides wireless access to a wired network.
-   **Firewall:** Enforces traffic-security rules.
-   **Modem/ONT:** Provides the physical interface to some ISP access
    technologies.

### Data units

  Layer/context   Common data unit
  --------------- --------------------------------
  Application     Data/message
  Transport       Segment (TCP) / Datagram (UDP)
  Network         Packet
  Data Link       Frame
  Physical        Bits

------------------------------------------------------------------------

# 2. Network categories

Network size and purpose often determine the category.

### PAN --- Personal Area Network

Very small area around one person.

Examples: - Bluetooth headset ↔ phone - Smartwatch ↔ phone

### LAN --- Local Area Network

A network in a home, room, office, floor, or building.

Characteristics: - Usually privately controlled - High speed - Ethernet
and Wi-Fi are common

### WLAN --- Wireless LAN

A LAN using wireless technologies such as Wi-Fi.

### MAN --- Metropolitan Area Network

Connects networks across a city/metropolitan region.

### WAN --- Wide Area Network

Connects geographically separated LANs.

Examples: - Branch office ↔ headquarters - Enterprise ↔ cloud provider -
ISP networks

### CAN --- Campus Area Network

Connects multiple buildings in a campus or organization.

### SAN --- Storage Area Network

A specialized high-speed network providing servers with access to shared
storage.

### Quick recall

**PAN \< LAN/CAN \< MAN \< WAN** is a useful size progression, although
real-world network classifications can overlap.

------------------------------------------------------------------------

# 3. Circuit switching vs packet switching

## Circuit switching

A dedicated communication path is established before data transfer.

### Mechanism

1.  Establish a circuit.
2.  Reserve/allocate communication resources.
3.  Transfer data.
4.  Tear down the circuit.

### Advantages

-   Predictable path
-   Historically useful for continuous voice
-   Dedicated resources can provide predictable behavior

### Disadvantages

-   Resources may remain reserved even when no useful data is being
    sent.
-   Less efficient for bursty computer traffic.

## Packet switching

Data is divided into packets.

Packets share network links with traffic from other flows.

### Mechanism

1.  Application generates data.
2.  Data is segmented/encapsulated.
3.  Packets travel through network devices.
4.  Packets are forwarded based on addressing/routing information.
5.  Destination reassembles/processes the data.

### Advantages

-   Efficient for bursty traffic
-   Shared infrastructure
-   Scales well for data networks

### Important idea

The Internet is fundamentally a **packet-switched network**.

------------------------------------------------------------------------

# 4. WAN technologies

## Leased line

A **leased line** is a dedicated point-to-point connection obtained from
a telecommunications provider.

### Characteristics

-   Dedicated connection between endpoints
-   Predictable performance
-   Often used between enterprise locations
-   Usually more expensive than shared services

### Example

`Branch A ===== dedicated provider circuit ===== HQ`

### Remember

**Leased line = dedicated path/service between sites.**

------------------------------------------------------------------------

## Metro Ethernet

Metro Ethernet provides Ethernet-based connectivity across a
metropolitan/provider network.

### Why use it?

Organizations can connect: - Offices - Data centers - Campuses

while using familiar Ethernet interfaces.

### Key idea

It extends Ethernet-style connectivity beyond a single LAN.

------------------------------------------------------------------------

## WiMAX

**WiMAX** is based on IEEE 802.16 and was designed for broadband
wireless access.

It can be used for: - Metropolitan wireless connectivity - Last-mile
broadband - Fixed or mobile broadband applications

### Exam note

WiMAX is historically important but is much less common today than
modern cellular and Wi-Fi deployments.

------------------------------------------------------------------------

# 5. Frame Relay

**Frame Relay** is a legacy packet-switched WAN technology.

### Core idea

Instead of a permanently dedicated physical circuit, traffic is carried
through virtual circuits.

Important terms: - **PVC:** Permanent Virtual Circuit - **DLCI:**
Data-Link Connection Identifier

### Why it mattered

Frame Relay allowed multiple logical WAN connections to share provider
infrastructure.

### Today

It is largely obsolete and is mainly useful for understanding legacy
networking.

------------------------------------------------------------------------

# 6. ATM --- Asynchronous Transfer Mode

ATM is a connection-oriented technology that uses fixed-size **53-byte
cells**:

-   5-byte header
-   48-byte payload

### Why fixed-size cells?

Fixed-size cells were useful for predictable switching and for carrying
different traffic types.

### Frame Relay vs ATM

  Feature          Frame Relay             ATM
  ---------------- ----------------------- --------------------------
  Basic unit       Variable-length frame   Fixed 53-byte cell
  WAN technology   Legacy                  Legacy
  Main idea        Virtual circuits        Virtual circuits + cells
  Modern use       Mostly obsolete         Mostly obsolete

### Memory hook

**ATM = Always Tiny Messages** → think **53-byte cells**.

------------------------------------------------------------------------

# 7. MPLS

**Multiprotocol Label Switching (MPLS)** forwards traffic using labels
rather than relying only on a normal IP longest-prefix lookup at every
forwarding point.

### Simplified mechanism

1.  Packet enters the MPLS network.
2.  An MPLS label is associated with the traffic.
3.  Provider routers/switching nodes forward based on labels.
4.  The label is changed/swapped as the packet travels.
5.  The packet exits the MPLS domain.

### Benefits

-   Efficient provider forwarding
-   Traffic engineering capabilities
-   Supports different services over provider infrastructure
-   Commonly associated with enterprise WAN services

### Key terms

-   **Label:** Short identifier used for forwarding.
-   **LSP:** Label Switched Path.
-   **PE router:** Provider Edge.
-   **P router:** Provider core router.

### Remember

**IP tells the network where the packet is going; MPLS labels can tell
the MPLS domain how to forward it.**

------------------------------------------------------------------------

# 8. Network topologies

A topology describes how devices/connections are arranged.

## Star

Every endpoint connects to a central device.

`PC ─┐` `PC ─┼─ Switch` `PC ─┘`

### Advantage

Failure of one endpoint cable normally affects only that endpoint.

### Disadvantage

Central-device failure can affect many devices.

------------------------------------------------------------------------

## Bus

All devices share a common backbone.

Legacy Ethernet used bus-style designs.

### Main problem

A physical break can affect a large part of the network.

------------------------------------------------------------------------

## Ring

Devices form a loop.

Each node has connections to neighboring nodes.

------------------------------------------------------------------------

## Mesh

Devices have multiple interconnections.

### Full mesh

Every device has a direct connection to every other device.

For `n` devices:

**Links = n(n − 1) / 2**

### Benefit

High redundancy.

### Cost

Many links/interfaces and greater complexity.

------------------------------------------------------------------------

## Hybrid

Combines two or more topology types.

Modern enterprise networks are often logically/physically hybrid.

------------------------------------------------------------------------

# 9. Peer-to-peer networking

In a **peer-to-peer (P2P)** network, devices can act as both clients and
resource providers.

There is no requirement for one central dedicated server.

### Advantages

-   Simple for small environments
-   Low initial cost
-   Easy resource sharing

### Disadvantages

-   Difficult centralized management
-   Security can become inconsistent
-   Backup and administration are harder at scale

### P2P vs client-server

  -----------------------------------------------------------------------
  P2P                                 Client-server
  ----------------------------------- -----------------------------------
  Distributed roles                   Centralized service model

  Good for small/simple networks      Better for larger managed
                                      environments

  Less centralized control            Centralized
                                      authentication/resources
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 10. Quick recall

-   **WAN:** connects geographically separated networks.
-   **Leased line:** dedicated provider connection.
-   **Metro Ethernet:** Ethernet-style metropolitan connectivity.
-   **WiMAX:** IEEE 802.16 wireless broadband technology.
-   **Frame Relay:** legacy packet-switched WAN using virtual circuits.
-   **ATM:** fixed 53-byte cells.
-   **MPLS:** label-based forwarding in provider networks.
-   **Circuit switching:** resources/path established for a circuit.
-   **Packet switching:** traffic divided into packets sharing links.
-   **P2P:** devices can directly provide resources to one another.

## Exam traps

-   Do not confuse **MPLS** with an Internet routing protocol.
-   Do not confuse **ATM cells** with Ethernet frames.
-   Do not assume every WAN connection is a dedicated physical circuit.
-   Do not confuse a **topology** with a network category such as
    LAN/WAN.
