# 🚀 CCNA Notes — Networking Fundamentals

Welcome to the CCNA Networking Fundamentals study notes. This document is formatted for clean presentation and easy navigation on GitHub.

---

## 📌 Table of Contents
- [1. Ping](#1-ping)
- [2. MAC Address](#2-mac-address)
- [3. IP Address](#3-ip-address)
- [4. MAC Address vs IP Address](#4-mac-address-vs-ip-address)
- [5. OSI Model](#5-osi-model)
- [6. OSI Layer 1 — Physical Layer](#6-osi-layer-1--physical-layer)
- [7. OSI Layer 2 — Data Link Layer](#7-osi-layer-2--data-link-layer)
- [8. OSI Layer 3 — Network Layer](#8-osi-layer-3--network-layer)
- [9. Layer 1 vs Layer 2 vs Layer 3](#9-layer-1-vs-layer-2-vs-layer-3)
- [10. MAC + IP Working Together](#10-mac--ip-working-together)
- [📝 Quick Revision & Summary](#-quick-revision--summary)

---

## 1. Ping

**Ping** is a network utility used to check whether a device is reachable over a network.

It uses **ICMP (Internet Control Message Protocol)** to send an Echo Request to a destination device. If the destination is reachable, it sends back an Echo Reply.

### 🛠️ How Ping Works
```text
Your PC
   |
   | 📨 ICMP Echo Request
   ↓
Destination Device
   |
   | 📨 ICMP Echo Reply
   ↓
Your PC
```

### 💻 Example
```bash
ping 8.8.8.8
```
> [!NOTE]
> If you receive replies, it generally means that the destination is reachable and there is network connectivity between the devices.

### 🔍 Ping Can Help Check:
- [x] Network connectivity
- [x] Whether a host is reachable
- [x] Packet loss
- [x] Approximate round-trip time (RTT)
- [x] Basic troubleshooting

> [!WARNING]
> **Important:** Ping does not prove that every network service is working. For example, a server may respond to ping while its web server is down.

---

## 2. MAC Address

**MAC (Media Access Control)** address is a hardware-level address used to identify a network interface on a local network.

- **OSI Layer:** Layer 2 — Data Link Layer

### 📋 Example
```text
00:1A:2B:3C:4D:5E
```
*A MAC address is typically represented as **48 bits (6 bytes)** in Ethernet networks.*

### 🎯 Purpose
MAC addresses are mainly used for communication inside a local network (**LAN**).

```text
PC A ──> Switch ──> PC B
```
The switch uses MAC addresses to decide which port should receive an Ethernet frame.

### 📊 MAC Address Table
A switch learns which MAC address is associated with which port.

| MAC Address | Switch Port |
| :--- | :--- |
| `AA:AA:AA:AA:AA:AA` | Port 1 |
| `BB:BB:BB:BB:BB:BB` | Port 2 |
| `CC:CC:CC:CC:CC:CC` | Port 3 |

---

## 3. IP Address

An **IP (Internet Protocol)** address is a logical address used to identify a device/interface at the network layer.

- **OSI Layer:** Layer 3 — Network Layer

### 🌐 Version Examples
- **IPv4 Example:** `192.168.1.10` *(32 bits long)*
- **IPv6 Example:** `2001:db8::1` *(128 bits long)*

### 🎯 Purpose
IP addresses are used to:
- Identify devices/interfaces logically
- Identify networks
- Enable communication between different networks
- Help routers determine where packets should go

```text
PC ──[IP Packet]──> Router ──> Internet ──> Server
```
*Routers primarily use IP addresses to make forwarding decisions.*

---

## 4. MAC Address vs IP Address

| Feature | MAC Address | IP Address |
| :--- | :--- | :--- |
| **Full Name** | Media Access Control | Internet Protocol |
| **Type** | Hardware/Link-layer address | Logical address |
| **OSI Layer** | Layer 2 | Layer 3 |
| **Main Use** | Local network communication | Communication between networks |
| **Used By** | Switches | Routers |
| **Example** | `00:1A:2B:3C:4D:5E` | `192.168.1.10` |
| **Address Size**| Usually 48-bit for Ethernet | IPv4: 32-bit \| IPv6: 128-bit |
| **Changes** | Usually associated with a network interface, but can be changed/spoofed | Can change depending on network/configuration |

### 💡 Simple Way to Remember
> 🗣️ **MAC:** "Who are you on this local network?"  
> 📍 **IP:** "Where are you on the network?"  
> *A simple analogy: MAC Address ──> Your identity at the local network level | IP Address ──> Your logical network location.*

---

## 5. OSI Model

The **OSI (Open Systems Interconnection)** model is a conceptual model that divides network communication into 7 layers. It helps us understand how data moves between devices and makes network troubleshooting easier.

### 🗺️ The 7 OSI Layers
```text
[Layer 7] ── Application
[Layer 6] ── Presentation
[Layer 5] ── Session
[Layer 4] ── Transport
[Layer 3] ── Network
[Layer 2] ── Data Link
[Layer 1] ── Physical
```

🗣️ **Mnemonic (From Layer 7 to Layer 1):**
> *"**A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing"*

---

## 6. OSI Layer 1 — Physical Layer

The Physical Layer is responsible for transmitting raw bits over a physical medium. It deals with the actual physical connection between devices.

- **Data Unit:** Bits
- **Examples:**
  - Ethernet cables, Fiber-optic cables
  - Radio signals, Electrical signals
  - Connectors & physical network interfaces
- **Devices/Technologies:** Cables, Hubs, Repeaters, Physical transceivers

### ⚡ Simple Example
When a network cable carries electrical or optical signals representing "0"s and "1"s, this is Layer 1 activity.
```text
10101010  ───[Physical Signals]───> Physical Medium
```

---

## 7. OSI Layer 2 — Data Link Layer

The Data Link Layer is responsible for communication between devices on the same local network/link. This layer works with MAC addresses and Ethernet frames.

- **Data Unit:** Frame
- **Important Address:** MAC Address
- **Common Device:** Switch
- **Main Responsibilities:** Framing, MAC addressing, local network communication, detecting certain transmission errors, controlling access to the network medium.

```text
PC A ──[Ethernet Frame]──> Switch ──> PC B
```
*The switch looks at the destination MAC address to determine where to forward the frame.*

---

## 8. OSI Layer 3 — Network Layer

The Network Layer is responsible for logical addressing and routing packets between different networks. This is where IP addresses and routers become important.

- **Data Unit:** Packet
- **Important Address:** IP Address
- **Common Device:** Router
- **Main Responsibilities:** Logical addressing, routing, packet forwarding, communication between different networks.

### 🗺️ Routing Example
Imagine two different networks:
```text
  Network A [192.168.1.0/24]
              |
              ↓
           Router (Examines Destination IP)
              |
              ↓
  Network B [10.0.0.0/24]
```

---

## 9. Layer 1 vs Layer 2 vs Layer 3

| Layer | Name | Main Concept | Address | Data Unit | Common Device |
| :---: | :--- | :--- | :---: | :---: | :--- |
| **1** | Physical | Signals & physical transmission | None | Bits | Hub / Repeater |
| **2** | Data Link | Local network & frames | MAC | Frame | Switch |
| **3** | Network | Routing between networks | IP | Packet | Router |

💡 **Easy Memory Trick:**  
`Layer 1 ──> Bits ──> Physical signals`  
`Layer 2 ──> Frames ──> MAC ──> Switch`  
`Layer 3 ──> Packets ──> IP ──> Router`  

---

## 10. MAC + IP Working Together

MAC and IP addresses have different jobs, but they work together during network communication.

```text
PC A ──> Switch ──> Router ──> Internet ──> Server
```

- **IP Address:** Used to determine the logical destination and routing path.
- **MAC Address:** Used for delivery across the current local Ethernet link.

### 📋 Header Breakdown Example
```text
Source IP      : 192.168.1.10  |  Source MAC      : PC A's MAC
Destination IP : 8.8.8.8       |  Destination MAC : Next-hop MAC (Router's Interface)
```
*The destination MAC on an Ethernet frame can represent the next hop, rather than the final destination across the Internet.*

> [!IMPORTANT]
> **Core Distinction:**  
> **IP** helps determine where the packet needs to go.  
> **MAC** helps deliver the frame across the current local link.

---

## 📝 Quick Revision

### 🔍 Ping
- Network connectivity testing tool
- Uses ICMP (Sends Echo Request, Receives Echo Reply)
- Can show latency and packet loss

### 🆔 MAC Address
- Layer 2 | Hardware/link-layer address
- Used for local network communication
- Switches use MAC addresses
- Ethernet frame contains source and destination MAC addresses

### 🌐 IP Address
- Layer 3 | Logical address
- Used for communication across networks
- Routers use IP addresses
- IPv4 = 32-bit | IPv6 = 128-bit

### ⚡ OSI Layers
- **OSI Layer 1 (Physical):** Bits ──> Signals ──> Cables ──> Physical transmission
- **OSI Layer 2 (Data Link):** Frames ──> MAC addresses ──> Switches ──> Local network communication
- **OSI Layer 3 (Network):** Packets ──> IP addresses ──> Routers ──> Routing between networks

---

## 📌 One-Line Summary
- **Ping** ──> Tests connectivity
- **MAC** ──> Layer 2 ──> Local delivery ──> Switch ──> Frame
- **IP** ──> Layer 3 ──> Network-to-network delivery ──> Router ──> Packet
- **Layer 1** ──> Physical ──> Bits
- **Layer 2** ──> Data Link ──> Frames + MAC
- **Layer 3** ──> Network ──> Packets + IP

---
