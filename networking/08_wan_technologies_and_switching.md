# Module 5: WAN Technologies & Switching Architectures

This module covers wide-area data transmission mechanics, analyzing historical packet-switching frameworks alongside modern high-speed enterprise telecommunications connectivity.

---

## 1. Circuit-Switched vs. Packet-Switched Networks

The core foundational split in wide-area data transmission architecture relies on how resource paths are carved out between endpoints.

### A. Circuit-Switched Networks
* **The Logic:** Establishes a **dedicated, continuous physical path** between two endpoints before transmission begins. No other user can utilize that physical line while the session is active, even if no data is being sent.
* **Analogy:** A traditional landline phone call (PSTN). Once connected, that wire path is yours entirely.
* **Pros/Cons:** Guaranteed bandwidth and zero variable delay (jitter); highly inefficient because idle time completely wastes expensive line resources.

### B. Packet-Switched Networks
* **The Logic:** Data is broken down into small chunks called **packets**. Each packet is tagged with source and destination metadata. Packets travel dynamically across a shared network mesh, taking different physical routes, and are reassembled at the destination.
* **Analogy:** The postal system. Multiple letters from different people travel inside the same mail truck over shared roads.
* **Pros/Cons:** Extremely efficient use of physical infrastructure; can cause variable delays (jitter) and out-of-order packets if congestion occurs.

---

## 2. Legacy Packet-Switching: Frame Relay vs. ATM

Before modern fiber optics dominated the planet, enterprises used these two Layer 2 WAN technologies over leased copper telephone grids.

### A. Frame Relay
* **The Concept:** A cost-effective packet-switched technology that handles variable-length frames. It stripped away complex error-checking mechanics from the network core, shifting that duty to end devices to maximize speeds over standard copper circuits.
* **Key Mechanic:** Uses **DLCI (Data Link Connection Identifier)** numbers to logically route traffic across a provider's shared cloud using Virtual Circuits (PVCs/SVCs).
* **Deficiency:** Variable-length frames cause unpredictable delay variations (jitter), making it terrible for modern voice and live streaming video applications.

### B. ATM (Asynchronous Transfer Mode)
* **The Concept:** Developed to fix Frame Relay’s delay predictability issues. Instead of variable frames, ATM forces **fixed-size 53-byte "cells"** across the wire.
* **The Structural Split:** Every cell is strictly composed of a 5-byte routing header and a 48-byte data payload.
* **The Logic:** Because every single chunk of data is exactly the same size, hardware switches can route traffic at blazing, mathematically predictable speeds without calculating frame buffers. This allowed flawless integration of voice, video, and data over a single connection.
* **Deficiency:** **"Cell Tax."** Spending 5 bytes of overhead for every 48 bytes of data means ~10% of total bandwidth is wasted strictly on infrastructure packaging.

---

## 3. MPLS (Multiprotocol Label Switching)

MPLS was engineered to combine the speed and predictability of ATM with the massive flexibility and scalability of standard IP Packet-Switching. It is the backbone of most modern enterprise WANs.

* **The Core Innovation:** Instead of analyzing long Layer 3 IP routing destination tables at every single router hop, MPLS appends a short, numeric **"Label"** to the packet header at the edge of the network.

### Standard Packet Hop-by-Hop:
`[Incoming Packet] ──> [Look up 32-bit IP in Routing Table] ──> [Find next Hop] (Slow)`

### MPLS Label Switching:
`[Incoming Packet] ──> [Read simple 20-bit Label Number] ──> [Swap Label & Route] (Extremely Fast)`

* **The Mechanics (Layer 2.5 Technology):** It sits between Layer 2 (Data Link) and Layer 3 (Network). Routers simply read the incoming label, look at a local label-forwarding table, swap the label for a new number, and shoot it out the interface instantly.
* **Cybersecurity Context (MPLS VPNs):** Providers use MPLS labels to completely isolate a corporation's traffic from other companies sharing the exact same physical fiber links. It creates secure, virtual corporate networks across public backbones without requiring heavy cryptographic processing.

---

## 4. Enterprise Leased Lines & Metro Ethernet

When companies want to link their headquarters to remote data centers, they utilize dedicated wide-area connections.

* **Leased Line WAN:**
  * **The Logic:** A private, dedicated, bidirectional point-to-point digital connection rented directly from a telecom provider (e.g., T1, T3, E1, E3 links).
  * **Security Advantage:** Total physical traffic isolation. Since the circuit is strictly dedicated to your company, outside interception or injection requires tapping the physical carrier lines.
  * **Downside:** Astronomically expensive and scales poorly across multiple sites.
* **Metro Ethernet WAN:**
  * **The Logic:** Extends standard LAN Ethernet technology (which you use inside buildings) across an entire metropolitan city area using high-speed carrier fiber optic grids.
  * **Why it replaced Leased Lines:** High cost-efficiency and extreme simplicity. Network engineers do not need to convert Ethernet traffic to complex WAN protocols like Frame Relay or T1 frames. The router simply outputs standard Ethernet frames directly into the provider's city grid.

---

## 5. Wireless WAN: Cellular Networking & WiMAX

* **Cellular Networking (WAN Access):**
  * **The Logic:** Uses localized cell towers to provide long-distance, high-speed internet transit over radio frequency bands. It scales from 3G (legacy IP), 4G LTE (IP-packet optimized), to **5G** (utilizing millimeter wave technologies for low latency).
  * **Security Focus:** High risk of rogue cellular interception (**IMSI-Catchers / Stingrays**). Enterprise endpoints must enforce application-layer encryption (TLS) and mandatory VPN connections when routing corporate traffic over cellular arrays.
* **WiMAX (Worldwide Interoperability for Microwave Access - IEEE 802.16):**
  * **The Logic:** A legacy wireless broadband technology designed to deliver high-speed internet across vast distances (up to 30 miles) as an alternative to cable or DSL infrastructure.
  * **The Current Status:** Largely phased out globally in favor of high-speed LTE and 5G cellular deployments.
