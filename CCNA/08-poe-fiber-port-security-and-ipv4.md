# CCNA Notes: EP-12 to EP-16

This file covers Power over Ethernet (PoE), Fiber Optics, Port Security, IPv4 Addressing classes, and foundational networking concepts.

---

## EP-12: Power over Ethernet (PoE)
Power over Ethernet (PoE) allows network cables to carry electrical power along with data over a single twisted-pair Ethernet cable to devices like **IP Phones**, wireless access points, and IP cameras.

### Types of PoE
* **Active PoE:** The power sourcing equipment (PSE) communicates with the connected device to negotiate the correct voltage before delivering power. If the device isn't PoE-compatible, no power is sent, protecting the hardware.
* **Passive PoE:** Delivers a constant, raw voltage down the cable regardless of the connected device. It does not perform a handshake, meaning plugging it into a non-PoE device can damage the hardware.

---

## EP-13: Fiber Optic Media
Fiber optic cables use pulses of light instead of electrical currents to transmit data, making them immune to electromagnetic interference (EMI) and highly efficient over long distances.

| Fiber Type | Core Diameter | Light Source | Distance Capability | Primary Use Case |
| :--- | :--- | :--- | :--- | :--- |
| **Single-Mode Fiber (SMF)** | Very narrow | Laser | Extremely long distances | WANs, campus backbones |
| **Multi-Mode Fiber (MMF)** | Wider core | LED / VCSEL | Shorter distances | Local LANs, data centers |

---

## EP-14: Port Security (Detailed)
Port Security is a Layer 2 traffic-control feature on Cisco switches that restricts input to an interface by limiting and identifying the MAC addresses of stations allowed to access the port. When a violation occurs, the switch can take protective actions (Protect, Restrict, or Shutdown the port).

---

## EP-15 & EP-16: IPv4 Addressing & Structure

An IPv4 address is a **32-bit address** (\(2^{32}\) total unique addresses) divided into **4 octets** (8 bits each), separated by dots. Each octet ranges from **0 to 255**.

### IPv4 Address Structure
* **Network Portion:** Identifies the specific network the host belongs to.
* **Host Portion:** Identifies the specific endpoint/device on that network.
* *Example:* In a standard setup, for the IP `192.168.1.209`, the network portion dictates where the packet travels globally, while the host portion (`209`) targets the specific machine.
* **Reserved Values:** The first address (Network ID, e.g., `.0`) and the last address (Broadcast ID, e.g., `.255`) are reserved and cannot be assigned to hosts.

### IPv4 Classes and Ranges

| Class | IP Address Range | Default Subnet Mask | Common Use Case |
| :---: | :--- | :--- | :--- |
| **A** | `1.0.0.0` – `126.255.255.255` | `255.0.0.0` | Very large networks |
| **B** | `128.0.0.0` – `191.255.255.255` | `255.255.0.0` | Medium to large networks |
| **C** | `192.0.0.0` – `223.255.255.255` | `255.255.255.0` | Small local networks (LANs) |
| **D** | `224.0.0.0` – `239.255.255.255` | *None* | Multicast traffic |
| **E** | `240.0.0.0` – `255.255.255.255` | *None* | Experimental / Research |

* **Loopback Address:** The entire `127.0.0.0` range (typically `127.0.0.1`) is skipped in the class layout because it is reserved for local host testing and diagnostic loopback functions.

### Host Capacity Example (Class B)
* For a standard Class B network like `128.0.0.0` with a subnet mask of `255.255.0.0`:
* Total available bits for hosts = 16 bits.
* Formula for assignable hosts: \(2^{16} - 2 = 65,534\) valid host IP addresses.

### NAT, ISPs, and IP Versions
* **Private IP Addresses:** IP blocks (like `192.168.0.0`) used strictly inside local home or corporate networks. They cannot route across the public internet directly.
* **NAT (Network Address Translation):** A method used by routers to translate private local IPs into a single public IP assigned by your **ISP** (Internet Service Provider, like AT&T) so local devices can browse the internet.
* **IPv4 vs IPv6 Scaling:**

| Protocol Version | Total Address Bit Space | Total Available Addresses |
| :---: | :--- | :--- |
| **IPv4** | 32 bits | \(2^{32}\) (~4.3 Billion addresses) |
| **IPv6** | 128 bits | \(2^{128}\) (Virtually infinite addresses) |
