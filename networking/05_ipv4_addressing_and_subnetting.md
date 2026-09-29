# Part 2: IPv4 Addressing & Subnetting

This note covers Internet Protocol version 4 (IPv4) concepts, structural properties, classful addressing, classless addressing (CIDR), and subnetting mechanics, detailed with security contexts and exam-focused insights.

---

## 1. IPv4 Properties & Structure

IPv4 operates at **Layer 3 (Network Layer)** of the OSI model. It is a connectionless, unreliable protocol responsible for end-to-end routing of packets across networks.

*   **Address Size:** 32 bits long.
*   **Format:** Written in **Dotted-Decimal Notation** (e.g., `192.168.1.1`).
*   **Structure:** Divided into 4 octets (8 bits per octet).
    *   Binary view: `11000000.10101000.00000001.00000001` (32 bits total).
*   **Components:** Every IP address consists of two parts:
    1.  **Network ID:** Identifies the specific network the host belongs to.
    2.  **Host ID:** Identifies the specific device/interface on that network.
*   **Security Insight:** Attackers use Layer 3 IP scanning (like `nmap -sn`) to map live hosts in a target network range. Understanding the network boundaries helps security engineers design strict Access Control Lists (ACLs).

---

## 2. Classful Addressing

Historically, the IP address space was divided into five distinct classes based on the leading bits of the first octet. 

| Class | First Octet Range (Decimal) | Leading Bits | Default Subnet Mask | Network / Host Split | Purpose / Use Case |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Class A** | `1.0.0.0` to `126.255.255.255` | `0` | `255.0.0.0` (/8) | 8 bits Net / 24 bits Host | Large commercial organizations |
| **Class B** | `128.0.0.0` to `191.255.255.255` | `10` | `255.255.0.0` (/16) | 16 bits Net / 16 bits Host | Medium to large companies |
| **Class C** | `192.0.0.0` to `223.255.255.255` | `110` | `255.255.255.0` (/24) | 24 bits Net / 8 bits Host | Small businesses, home LANs |
| **Class D** | `224.0.0.0` to `239.255.255.255` | `1110` | N/A | No host division | **Multicast traffic** |
| **Class E** | `240.0.0.0` to `255.255.255.255` | `1111` | N/A | No host division | Experimental / Research |

### Special and Reserved IP Ranges (CompTIA Network+ Must-Know)
*   **Loopback Address (`127.0.0.0/8`):** Used by a host to send network traffic to itself (most commonly `127.0.0.1`). Used to test the local TCP/IP stack implementation.
*   **APIPA (Automatic Private IP Addressing - `169.254.0.0/16`):** If a Windows host is configured for DHCP but cannot communicate with a DHCP server, it automatically assigns itself an address from this link-local range. **Security Warning:** Seeing an APIPA address on your endpoint means DHCP failure or a network disconnection/segmentation issue.

### Private IP Addresses (RFC 1918)
These addresses are non-routable on the public internet. They are used internally within private LANs to conserve IPv4 space.

*   **Class A Private:** `10.0.0.0` to `10.255.255.255` (`10.0.0.0/8`)
*   **Class B Private:** `172.16.0.0` to `172.31.255.255` (`172.16.0.0/12`)
*   **Class C Private:** `192.168.0.0` to `192.168.255.255` (`192.168.0.0/16`)

---

## 3. Classless Addressing (CIDR)

Classful addressing wasted billions of IP addresses. To solve this, **CIDR (Classless Inter-Domain Routing)** was introduced.

*   **Concept:** Eliminates the rigid Class A, B, and C default boundaries. Networks can be segmented at any arbitrary bit boundary.
*   **CIDR Notation:** Appends a forward slash (`/`) followed by the number of bits turned on for the network prefix (e.g., `192.168.1.0/26`).
*   **Subnet Mask vs CIDR:** A mask tells the router which part is the network.
    *   `/24` in binary is 24 ones: `11111111.11111111.11111111.00000000` = `255.255.255.0`
    *   `/26` in binary is 26 ones: `11111111.11111111.11111111.11000000` = `255.255.255.192`

---

## 4. Subnetting Mechanics

Subnetting is the practice of dividing a single large network into multiple, smaller sub-networks (subnets).

### Why Subnet?
1.  **Security Segmentation:** Isolates sensitive departments (e.g., HR, Finance) from standard user segments or public DMZs. If an attacker compromises a machine in one subnet, they cannot easily sniff or pivot to another subnet without passing through a Layer 3 firewall/router.
2.  **Performance:** Reduces the size of the **broadcast domain**, minimizing broadcast traffic congestion.
3.  **Efficiency:** Better utilization of limited IP address spaces.

### Core Mathematical Formulas
*   **Number of Created Subnets:** \(2^s\) (where \(s\) is the number of bits borrowed from the host portion).
*   **Number of Usable Hosts per Subnet:** \(2^h - 2\) (where \(h\) is the number of remaining host bits).
    *   *Why subtract 2?* Because every subnet reserves the **first address** as the Network ID and the **last address** as the Broadcast ID.

### Subnetting Step-by-Step Example
**Problem:** Subnet the network `192.168.1.0/24` to create 4 distinct networks for security segregation.

1.  **Determine bits to borrow:** We need 4 subnets. \(2^s = 4 \implies s = 2\) bits.
2.  **Calculate new CIDR mask:** Original was `/24`. Add borrowed bits: \(24 + 2 = /26\).
    *   New Subnet Mask: `255.255.255.192`
3.  **Calculate remaining host bits:** Total bits (32) - Custom Prefix (26) = 6 bits (\(h=6\)).
4.  **Calculate usable hosts per subnet:** \(2^6 - 2 = 64 - 2 = 62\) usable host IPs per network.
5.  **Determine the Block Size (Magic Number):** \(256 - \text{Interesting Octet Mask Value} \implies 256 - 192 = 64\). (The subnets increment by 64).

#### Breakdown of the 4 Created Subnets:

| Subnet Number | Network ID | Usable Host IP Range | Broadcast Address |
| :--- | :--- | :--- | :--- |
| **Subnet 1** | `192.168.1.0` | `192.168.1.1` to `192.168.1.62` | `192.168.1.63` |
| **Subnet 2** | `192.168.1.64` | `192.168.1.65` to `192.168.1.126` | `192.168.1.127` |
| **Subnet 3** | `192.168.1.128` | `192.168.1.129` to `192.168.1.190` | `192.168.1.191` |
| **Subnet 4** | `192.168.1.192` | `192.168.1.193` to `192.168.1.254` | `192.168.1.255` |

### VLSM (Variable Length Subnet Masking)
*   **Concept:** Applying subnetting recursively. Instead of cutting a network into equal-sized chunks, VLSM allows you to create subnets of varying sizes based on the specific host requirements of each department.
*   **Design Strategy:** Always subnet for the largest host requirements first, then work down to the smaller needs (such as `/30` or `/31` point-to-point links between routers).
*
