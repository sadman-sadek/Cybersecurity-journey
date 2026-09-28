# Network Devices & Security Essentials

This file covers the fundamental networking devices operating at different OSI layers, along with key security and traffic management components.

---

## 1. Layered Network Devices
Devices categorized by the OSI model layer they operate on:
* **Layer 1 Devices (Physical Layer):** 
  * *Examples:* Hubs, Repeaters, Cables.
  * *Function:* They deal with raw bitstreams and electrical signals. They do not read MAC or IP addresses; they simply replicate and broadcast signals.
* **Layer 2 Devices (Data Link Layer):** 
  * *Examples:* Switches, Network Interface Cards (NICs), Bridges.
  * *Function:* They use **MAC addresses** to forward data frames to specific devices within the same local network (LAN).
* **Layer 3 Devices (Network Layer):** 
  * *Examples:* Routers, Multilayer Switches.
  * *Function:* They use **IP addresses** to route packets across different networks and determine the best path for data.

---

## 2. Network Security Elements
* **Firewall:** 
  * A security system that monitors and controls incoming and outgoing network traffic based on predetermined security rules. Acts as a barrier between a trusted and an untrusted network.
* **IDS (Intrusion Detection System):** 
  * A passive monitoring system that detects suspicious activities or policy violations and generates alerts.
* **IPS (Intrusion Prevention System):** 
  * An active control system that not only detects threats but also automatically takes action to block or prevent them.

---

## 3. Traffic Management & Optimization
* **Load Balancer:** 
  * A device or software that distributes incoming network or application traffic across multiple servers to prevent overload and ensure high availability.
* **Proxy Server:** 
  * An intermediary server between a client (user) and the internet. It provides anonymity, content filtering, security, and caching to speed up requests.
