# 🌐 Computer Networking Foundation - Class 01

## 1. Network Switch
A **Switch** is an intelligent Local Area Network (LAN) device that connects multiple end-devices (such as PCs, Servers, and Printers) within the same network.

### 🔑 Core Concepts
* **Layer 2 Device:** Operates at the **Data Link Layer** of the OSI model.
* **MAC Address Table:** It is intelligent; it learns and maps the **MAC Addresses** of all connected devices to their respective ports using a CAM (Content Addressable Memory) table.
* **Unicast Communication:** Unlike a Hub, a Switch sends data packets *only* to the specific destination port instead of broadcasting it to everyone.
* **Collision Domain:** Every single port on a switch represents a separate **Collision Domain**, preventing data packet collisions.

### 🎯 Cyber Security Perspective
* **MAC Flooding Attack:** Attackers can flood the switch's CAM table with fake MAC addresses. Once the table is full, the switch fails open and acts like a **Hub**, broadcasting all traffic. This allows the attacker to sniff sensitive network data easily.
* **Port Security:** A critical defense mechanism where network administrators restrict a switch port to only allow specific, authorized MAC addresses.

---

## 2. WAP (Wireless Access Point)
A **WAP** is a hardware device that connects to a wired network infrastructure (like a switch or router) and projects a **Wireless (Wi-Fi) signal** for target devices.

### 🔑 Core Concepts
* **Bridge between Wired & Wireless:** It acts as a bridge, transforming physical ethernet cable connectivity into radio waves.
* **Shared Medium:** Wi-Fi operates on a shared medium. As more devices connect to a single WAP, the available bandwidth gets shared, which can lower individual speeds.
* **Half-Duplex:** Devices connected via a standard WAP can either transmit or receive data at a single moment, not both simultaneously.

### 🎯 Cyber Security Perspective
* **Rogue AP:** An unauthorized Access Point installed on a secure network without the administrator's knowledge. Attackers use this to bypass network security controls and sniff corporate data.
* **Encryption Protocols:** WAPs secure wireless data using encryption like **WPA2** or the more secure **WPA3**. Attackers often attempt to capture the **Wi-Fi Handshake** to launch offline brute-force attacks on weak passwords.
* **SSID Hiding:** Disabling SSID broadcasting makes the wireless network name invisible to casual scans, adding a minor layer of obfuscation.

---

### 📝 Quick Revision Cheat Sheet
* **Switch** = The smart traffic cop of the internal network (knows exactly who lives where and directs packets accordingly).
* **WAP** = The bridge that turns physical cables into an invisible Wi-Fi zone.
*
