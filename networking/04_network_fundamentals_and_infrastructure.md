# Part 1: Network Fundamentals & Physical Infrastructure

This note covers the foundational elements of computer networking, focusing on network categories, topologies, physical cabling infrastructure, and associated tools. Security implications and CompTIA Network+ exam objectives are integrated throughout.

---

## 1. Categories of Networks

Networks are categorized primarily by their geographic scale, ownership, and operational scope.

*   **PAN (Personal Area Network):**
    *   **Scale:** Centered around a single person in a single location (typically within 10 meters).
    *   **Technologies:** Bluetooth, Zigbee, NFC.
    *   **Security Focus:** High risk of **Bluejacking** (sending unsolicited messages) and **Bluesnarfing** (unauthorized access of data via Bluetooth). Ensure discoverability is turned off when not needed.
*   **LAN (Local Area Network):**
    *   **Scale:** Connects computers and devices within a limited geographical area, such as a home, school, office building, or laboratory.
    *   **Technologies:** Ethernet (802.3), Wi-Fi (802.11).
    *   **Security Focus:** Internal threats, rogue access points, ARP poisoning, and MAC spoofing. Network segmentation using VLANs is crucial here.
*   **WLAN (Wireless Local Area Network):**
    *   **Scale:** A LAN that uses wireless network technology.
    *   **Security Focus:** Highly susceptible to eavesdropping and unauthorized access. Modern implementation requires **WPA3** encryption. Avoid legacy WEP or WPA/WPA2 with weak pre-shared keys. Watch out for **Evil Twin** attacks.
*   **MAN (Metropolitan Area Network):**
    *   **Scale:** Covers a larger geographic area than a LAN but smaller than a WAN, such as a city or a large university campus.
    *   **Ownership:** Often owned by a consortium of users or a single network provider (e.g., Metro Ethernet).
*   **WAN (Wide Area Network):**
    *   **Scale:** Spans a large physical distance, connecting multiple LANs across cities, countries, or continents. The Internet is the largest example of a WAN.
    *   **Security Focus:** Data in transit across public infrastructure must be secured using **IPsec VPNs** or Transport Layer Security (TLS) to ensure confidentiality and integrity.
*   **SAN (Storage Area Network):**
    *   **Scale:** A specialized, high-speed network that provides block-level network access to storage.
    *   **Protocols:** Fibre Channel (FC), iSCSI.
    *   **Security Focus:** Target for ransomware. Access Control Lists (ACLs), fabric zoning, and storage encryption are critical defense mechanisms.

---

## 2. Network Topologies & Architecture

The structure of a network, including how devices connect and interact.

### Physical and Logical Topologies
*   **Star Topology:**
    *   **Design:** All end devices connect directly to a central hub or switch.
    *   **Pros/Cons:** Easy to troubleshoot; if one cable fails, only that node goes down. However, the central switch represents a **Single Point of Failure (SPOF)**.
    *   **Security Focus:** Centralized monitoring via network taps or SPAN ports on the switch is highly efficient for IDS/IPS deployment.
*   **Mesh Topology (Full vs. Partial):**
    *   **Design:** Every node connects to every other node (Full Mesh), or selected nodes connect to multiple others (Partial Mesh).
    *   **Formula for Full Mesh Links:** $n(n-1) / 2$ (where $n$ is the number of nodes).
    *   **Pros/Cons:** Maximum redundancy and fault tolerance. Highly expensive and complex to wire physically.
    *   **Security Focus:** Provides high availability (HA), protecting against physical denial-of-service (DoS) attacks caused by severed lines.
*   **Bus Topology:**
    *   **Design:** Devices share a single central cable (the "bus" or backbone). Requires terminators at both ends to prevent signal reflection.
    *   **Security Focus:** Highly insecure. Every node can intercept packets meant for other nodes because it acts as a shared collision domain. Legacy tech, rarely seen today.
*   **Ring Topology:**
    *   **Design:** Devices are connected in a circular loop. Data travels in one direction (or dual directions in FDDI/SONET for redundancy) using a "token".
*   **Hybrid Topology:**
    *   **Design:** A combination of two or more distinct topologies (e.g., Star-Bus or Star-Ring like Token Ring over Cat cables). Most modern corporate infrastructures are hybrid.

### Architecture: Peer-to-Peer (P2P) vs. Client-Server
*   **Peer-to-Peer (P2P) Network:**
    *   **Concept:** Decentralized architecture where each workstation (peer) has equivalent capabilities and responsibilities. There is no central server.
    *   **Security Risks:**
        *   **Lack of Centralized Control:** No central firewall or authentication mechanism; hard to enforce security policies.
        *   **Malware Distribution:** Piracy networks using protocols like BitTorrent are frequently weaponized to distribute trojans and spyware.
        *   **Data Leakage:** Users might inadvertently expose sensitive corporate directories to the public P2P network.

---

## 3. Physical Cabling Infrastructure

The Physical Layer (Layer 1 of the OSI model) forms the bedrock of network security and availability.

### A. Twisted Pair Cabling
Consists of pairs of insulated copper wires twisted together to reduce **EMI (Electromagnetic Interference)** and **Crosstalk** (signal bleeding between adjacent wires).

*   **UTP (Unshielded Twisted Pair):** Common, flexible, and inexpensive. Vulnerable to external EMI and physical wiretapping (sniffing emissions using induction devices).
*   **STP (Shielded Twisted Pair):** Includes a metallic foil shielding to guard against EMI. Requires proper grounding. Used in industrial environments or high-interference zones.

#### Ethernet Cable Categories (CompTIA Network+ Crucial Reference)

| Category | Max Data Rate | Max Bandwidth | Max Distance | Common Use Cases |
| :--- | :--- | :--- | :--- | :--- |
| **Cat 5e** | 1 Gbps | 100 MHz | 100 meters | Standard legacy gigabit LANs |
| **Cat 6** | 10 Gbps | 250 MHz | 37-55 meters | Standard modern setups (10G at short reach) |
| **Cat 6a** | 10 Gbps | 500 MHz | 100 meters | Standard for modern data centers (Full 10G) |
| **Cat 7** | 10 Gbps | 600 MHz | 100 meters | Fully shielded, reduced crosstalk |
| **Cat 8** | 25-40 Gbps | 2000 MHz | 30 meters | Switch-to-switch data center links |

#### Connectors
*   **RJ-45:** Standard 8-pin connector used for Ethernet networks.
*   **RJ-11:** 4 or 6-pin connector used for traditional telephone and DSL lines.

### B. Coaxial Cabling
Consists of a copper core surrounded by insulation, a metallic shield, and an outer jacket. Highly resistant to EMI.
*   **RG-6:** Used for modern cable television, satellite, and cable broadband modems.
*   **RG-59:** Used for older analog video connections and legacy CCTV implementations.
*   **BNC Connector:** Bayonet Neill–Concelman connector, used to terminate coaxial cables.

### C. Fiber Optic Cabling
Transmits data as light pulses through glass or plastic strands. 
*   **Security Advantage:** Immune to EMI, RFI, and traditional physical copper wiretapping methods. Any physical breach or bending alters light transmission, which triggers detection mechanisms instantly.

#### Types of Fiber Optic Cables
1.  **Single-Mode Fiber (SMF):**
    *   **Core Size:** Very narrow (typically ~9 microns).
    *   **Light Source:** Laser.
    *   **Distance:** Long-haul distribution (up to tens of kilometers without repeaters). Used for WAN backbones.
2.  **Multi-Mode Fiber (MMF):**
    *   **Core Size:** Wider (50 or 62.5 microns). Allows multiple paths (modes) of light to travel.
    *   **Light Source:** LED.
    *   **Distance:** Short distances (typically up to 550 meters at 10Gbps). Used within buildings or local server rooms.

#### Fiber Connectors
*   **ST (Straight Tip):** Bayonet-style twist lock (legacy, looks like a BNC connector).
*   **SC (Subscriber Connector):** Square, push-pull snap mechanism.
*   **LC (Lucent Connector):** Small form factor, retaining tab (looks like a mini RJ-45). Popular in high-density deployments.
*   **MTRJ (Mechanical Transfer Registered Jack):** Duplex connector enclosing two fibers in a single modular plug.

---

## 4. Media Converters & Cabling Tools

### Media Converters
Operate at Layer 1 to connect completely different media types together (e.g., Copper Ethernet to Fiber Optic, Single-mode to Multi-mode fiber).
*   **Security/Architectural Note:** Extending a network's reach via fiber converters can unintentionally bypass physical perimeter defenses. Ensure the converted endpoint terminates in a physically secure facility.

### Cabling Tools (Troubleshooting & Verification)
*   **Crimper:** Attaches connectors (like RJ-45 or RJ-11) to the stripped ends of a cable.
*   **Cable Stripper:** Removes the outer protective plastic jacket from cables without cutting the internal wires.
*   **Punchdown Tool:** Forces wires into insulation-displacement connectors on patch panels and keystone jacks.
*   **Tone Generator and Probe (Fox and Hound):** Used to trace a specific wire through a bundle or wall cavity. The generator injects an audio tone into the wire, and the inductive probe detects it.
*   **Cable Tester (Continuity Tester):** Checks if the pins are wired correctly on both ends and verifies there are no opens or shorts in the copper lines.
*   **TDR (Time Domain Reflectometer):** Sends electrical pulses down a copper cable to find the exact location of a break, short, or bend by measuring signal bounce-back time.
*   **OTDR (Optical TDR):** The equivalent tool used for Fiber Optic cables to find fractures, bad splices, or physical bends.
*
