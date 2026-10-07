# CCNA Notes: Enterprise Campus Network Architectures

This note explores standard network architecture designs, common application layer protocols, and transitioning from traditional designs to prevent single points of failure, based on **NetworkChuck CCNA Episodes 6 and 7**.

---

## 🛠️ Common Application Layer Protocols
*   **DHCP:** Dynamically assigns IP addresses to devices on a network.
*   **FTP vs SFTP:** FTP is unencrypted and unsafe; **SFTP (Secure FTP)** uses SSH to encrypt file transfers safely.
*   **SMTP:** Used for sending emails.
*   **HTTP:** Web browsing (unencrypted).
*   **SNMP:** Used for monitoring and managing network devices.
*   **TFTP:** Trivial FTP; a simplified, connectionless (UDP-based) version of FTP used for quick boot loading or firmware transfers.

---

## 🏗️ Campus Network Design Paradigms

Traditional networks suffer from **Single Points of Failure** if they only rely on one router or path. Modern enterprise architecture adds redundancy through layered structures.

### 1. Two-Tier Architecture (Collapsed Core)
Ideal for smaller to medium-sized networks. It collapses the Core and Distribution functions into a single layer.

```text
       [ Router ]
           │
 ┌───────────────────┐
 │ Multilayer Switch │  <-- Collapsed Core / Distribution Layer (Layer 3)
 └─┬───────┬───────┬─┘
   │       │       │
 [Sw1]   [Sw2]   [Sw3]  <-- Access Layer (Layer 2)
  │ │     │ │     │ │
 [PCs]  [PCs]  [Servers]
```
*   **Access Layer:** Where end devices (PCs, laptops, printers, servers) connect directly to the switches.
*   **Collapsed Core/Distribution Layer:** Handles routing, security filtering, and aggregates access layer connections.

### 2. Three-Tier Architecture
Designed for large-scale enterprise campuses. It keeps the Core, Distribution, and Access layers completely separated for maximum scalability and stability.

*   **Core Layer:** The high-speed backbone of the network. Its only job is to switch traffic as fast as possible between Distribution blocks.
*   **Distribution Layer:** Acts as the boundary between Layer 2 switching and Layer 3 routing. Implements security policies, ACLs, and routing.
*   **Access Layer:** Connects the user devices to the network.
*
