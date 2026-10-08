#  Network Connectivity and WAN Technologies

This section covers the fundamentals of local and wide-area networks, along with various Wide Area Network (WAN) technologies and topology architectures used to connect enterprise networks.

## Core Network Types

*   **LAN (Local Area Network):** A network that connects computers and devices within a limited geographical area, such as a home, school, office building, or laboratory.
*   **WAN (Wide Area Network):** A telecommunications network that extends over a large geographical area (e.g., across cities, states, or countries) to connect multiple LANs.

---

## WAN Technologies & Connectivity Options

### 1. MPLS (Multiprotocol Label Switching)
*   **Definition:** A high-performance telecommunications network architecture that directs data from one network node to the next based on short **path labels** rather than long network addresses.
*   **Key Benefit:** Avoids complex lookups in a routing table, speed up traffic flow, and highly reliable for enterprise connections.

### 2. Point-to-Point Connection
*   A dedicated, direct communication link between two network nodes or endpoints (e.g., a leased line connecting a corporate office directly to a data center).

### 3. Carrier Ethernet Services
*   **E-LAN (Ethernet LAN):** A multipoint-to-multipoint service that connects two or more Customer Edge (CE) devices, making the WAN look like a single distributed local Ethernet switch.
*   **E-Tree (Ethernet Tree):** A point-to-multipoint service providing a rooted topology. It restricts communication so that "leaf" nodes can talk only to "root" nodes, not to each other.

### 4. SD-WAN (Software-Defined Wide Area Network)
*   An architectural approach that uses software-defined networking (SDN) principles to manage and operate WAN connections. It dynamically routes traffic over multiple transport links (like MPLS, LTE, Broadband) based on real-time network conditions.

---

## Architectural Layout

In an enterprise topology connecting a **Corporate Office** and a **Data Center (e.g., Dallas)**:
*   **CE (Customer Edge):** The router or equipment located on the customer's premises that connects directly to the service provider's network edge.
