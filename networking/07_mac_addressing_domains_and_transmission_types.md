# Part 4: MAC Addressing, Network Domains & Transmission Modes

This note breaks down the hardware-level logic of Layer 2 (Data Link Layer), how networks segment traffic to prevent collisions and chaos, and how devices communicate mechanically across physical links.

---

## 1. The Logic of a MAC Address (Physical Identity)

While an IP address (Layer 3) is a logical address that changes based on *where* you connect, a **MAC (Media Access Control) Address** is a permanent, physical identity burned into the network interface card (NIC) at the factory.

*   **Size:** 48 bits long.
*   **Format:** Written as 12 hexadecimal characters, divided into 6 pairs separated by colons or hyphens (e.g., `00:1A:2B:3C:4D:5E`).
*   **The Structural Split:** A MAC address is split exactly down the middle:

\[\underbrace{\text{00 : 1A : 2B}}_{\text{OUI (Organizationally Unique Identifier)}} \quad - \quad \underbrace{\text{3C : 4D : 5E}}_{\text{UAA (Universally Administered Address)}}\]

1.  **OUI (First 24 bits):** Identifies the vendor/manufacturer (e.g., Cisco, Intel, Apple). Security analysts use this during incidents to instantly identify what device type (like an IoT camera or a specific laptop vendor) just joined the network.
2.  **UAA (Last 24 bits):** A unique serial number assigned by the manufacturer to that specific chip.

### Cybersecurity Context: MAC Spoofing & Sniffing
*   **MAC Spoofing:** Attackers can easily change their software configuration to copy a legitimate device's MAC address. This is frequently used to bypass **MAC Filtering** on Wi-Fi networks or captive portals.
*   **MAC Flooding:** An attack directed at switches. The attacker floods the switch with thousands of fake MAC addresses, filling up its **CAM (Content Addressable Memory) Table**. When full, the switch fails securely into a "hub mode," broadcasting all network traffic to every port, allowing the attacker to sniff sensitive data.

---

## 2. Collision Domains vs. Broadcast Domains

Understanding domains is the key to knowing how modern network devices (Hubs, Switches, and Routers) handle and isolate traffic.

### A. Collision Domain (Layer 1 / Layer 2 boundary)
A physical segment of a network where packets can collide with one another if two devices transmit data at the exact same time.

*   **The Hub Concept:** Legacy hubs create **one giant collision domain** across all ports. If Device A talks, everyone else must wait, or a collision occurs.
*   **The Switch Concept:** Modern switches break up collision domains. **Every single port on a switch is its own private collision domain.** Device A and Device B can transmit simultaneously on different ports without interference.

### B. Broadcast Domain (Layer 3 boundary)
A logical network segment in which any device can transmit a broadcast frame, and every other device on that same segment will receive a copy of it.

*   **Switches:** Forward broadcasts out of **every single port** except the one it arrived on. Therefore, an entire switch (and all connected switches) forms **one large broadcast domain**.
*   **Routers:** **Block broadcasts.** Routers do not forward Layer 2 broadcast frames across networks. They break up broadcast domains.

<layout>
  edugraph(lookup=edugraph(code="""
import matplotlib.pyplot as plt
import matplotlib.patches as patches

fig, (ax1, ax2) = plt.subplots(1, 2, figsize=(12, 6))

# Left Plot: Switch (Collision Isolation)
ax1.set_title("Modern Switch Architecture", fontsize=14, fontweight='bold', pad=15)
ax1.add_patch(patches.Rectangle((0.3, 0.4), 0.4, 0.2, facecolor='#1f77b4', edgecolor='black', alpha=0.8))
ax1.text(0.5, 0.5, "SWITCH", ha='center', va='center', color='white', fontweight='bold', fontsize=12)

# Ports & Hosts
ports = [(0.1, 0.7), (0.1, 0.3), (0.9, 0.7), (0.9, 0.3)]
for i, (hx, hy) in enumerate(ports):
    ax1.plot([0.5, hx], [0.5, hy], color='black', linestyle='--', zorder=1)
    ax1.add_patch(patches.Circle((hx, hy), 0.06, facecolor='#2ca02c', edgecolor='black', zorder=2))
    ax1.text(hx, hy, f"Host {i+1}", ha='center', va='center', color='white', fontsize=9, fontweight='bold')
    
    # Indicate distinct collision domains
    mid_x, mid_y = (0.5 + hx)/2, (0.5 + hy)/2
    ax1.add_patch(patches.Circle((mid_x, mid_y), 0.04, facecolor='none', edgecolor='red', linewidth=1.5))
    ax1.text(mid_x, mid_y+0.05, "CD", color='red', fontsize=8, ha='center')

ax1.text(0.5, 0.1, "4 Ports = 4 Collision Domains\n1 Broadcast Domain", ha='center', color='darkblue', fontsize=11, fontweight='bold')
ax1.set_xlim(0, 1)
ax1.set_ylim(0, 1)
ax1.axis('off')

# Right Plot: Router (Broadcast Isolation)
ax2.set_title("Router Boundary Architecture", fontsize=14, fontweight='bold', pad=15)
ax2.add_patch(patches.Circle((0.5, 0.5), 0.12, facecolor='#d62728', edgecolor='black', alpha=0.8))
ax2.text(0.5, 0.5, "ROUTER", ha='center', va='center', color='white', fontweight='bold', fontsize=12)

# Networks
ax2.plot([0.1, 0.38], [0.5, 0.5], color='black', linewidth=2)
ax2.plot([0.62, 0.9], [0.5, 0.5], color='black', linewidth=2)

ax2.add_patch(patches.Rectangle((0.05, 0.25), 0.25, 0.5, facecolor='none', edgecolor='orange', linewidth=2, linestyle=':'))
ax2.text(0.175, 0.65, "Broadcast\nDomain 1", color='orange', fontweight='bold', ha='center', fontsize=10)

ax2.add_patch(patches.Rectangle((0.7, 0.25), 0.25, 0.5, facecolor='none', edgecolor='purple', linewidth=2, linestyle=':'))
ax2.text(0.825, 0.65, "Broadcast\nDomain 2", color='purple', fontweight='bold', ha='center', fontsize=10)

ax2.text(0.5, 0.1, "Routers Stop Broadcast Traffic Cold\nCreates Isolated Networks", ha='center', color='darkred', fontsize=11, fontweight='bold')
ax2.set_xlim(0, 1)
ax2.set_ylim(0, 1)
ax2.axis('off')

import io
import base64
buf = io.BytesIO()
plt.savefig(buf, format='png', bbox_inches='tight')
buf.seek(0)
base64_str = base64.b64encode(buf.read()).decode('utf-8')
plt.close()
print(f'base64_encoded_image:"data:image/png;base64,{base64_str}"')
"""))
</layout>

#### Summary Matrix for Exam Quick-Recall:

| Device | Layer | Collision Domains | Broadcast Domains |
| :--- | :--- | :--- | :--- |
| **Hub** | Layer 1 | 1 Shared Domain (All ports) | 1 Shared Domain |
| **Switch** | Layer 2 | Per-Port Domain (Isolated) | 1 Shared Domain |
| **Router** | Layer 3 | Per-Port Domain (Isolated) | Per-Port Domain (Isolated) |

---

## 3. Physical Transmission Control (Duplexing)

Devices need rules on how they share physical copper wires or fiber strands to avoid data corruption.

### A. Half-Duplex (HDX)
*   **The Logic:** Devices can send data and receive data, but **not at the same time**. It works like a walkie-talkie (one person talks, the other listens; if both talk, the signal destroys itself).
*   **Tech Associations:** Legacy hubs, Wi-Fi networks (802.11 operates inherently in half-duplex because they share the air medium).
*   **The Traffic Cop Protocol (CSMA/CD):** 
    *   Stands for **Carrier Sense Multiple Access with Collision Detection**. 
    *   *How it works logically:* Before talking, a host listens to the wire. If it's quiet, it sends data. If two devices talk at once, a collision happens. They instantly detect it, send a "jam signal," stop transmitting, wait a random amount of milliseconds (Exponential Backoff), and try again.

### B. Full-Duplex (FDX)
*   **The Logic:** Devices can send and receive data **simultaneously**. It works like a modern telephone conversation. 
*   **Tech Associations:** Modern switches configured with twisted-pair or fiber-optic connections. 
*   **Why it's better:** Since sending and receiving utilize completely separate physical wires inside the cable, **collisions are mathematically impossible**. CSMA/CD is completely disabled in full-duplex environments.
*
