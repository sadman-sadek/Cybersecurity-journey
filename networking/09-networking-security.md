# Cybersecurity-Focused Networking Revision Guide


---

## 🛠️ Part 1: Routing Concepts, Protocols & High Availability

### 1. Basic Routing Concepts (Static vs. Dynamic Routing)
* **Static Routing:** Manually configured paths mapping networks to specific next-hops.
  * *Security Perspective:* Highly secure for small, predictable environments as it prevents **Route Poisoning** or unauthorized route injection. However, it lacks scalability and is prone to human misconfiguration (Security Holes).
* **Dynamic Routing:** Routers automatically discover paths and update routing tables using protocols.
  * *Security Perspective:* High risk of malicious route advertisements. To prevent rogue routers from altering traffic paths, cryptographic authentication (**MD5/SHA**) must be enforced on all routing updates.

### 2. Routing Matrix & Route Aggregation
* **Routing Matrix:** The internal calculation mechanism used by a router to determine the optimal path for packet forwarding.
* **Route Aggregation (Supernetting):** Combining multiple contiguous subnets into a single routing advertisement.
  * *Security Perspective:* Shrinks the global routing table and hides internal network topology. This minimizes the **Attack Surface** and simplifies the implementation of strict Access Control Lists (ACLs).

### 3. Interior vs. Exterior Gateway Protocols (IGP vs. EGP)
* **IGP (e.g., OSPF, EIGRP):** Used for routing within a single Autonomous System (AS).
  * *Security Perspective:* Vulnerable to internal reconnaissance. Securing IGPs requires configuring **Passive Interfaces** on user-facing ports and utilizing route filtering to isolate internal segments.
* **EGP (e.g., BGP):** Used for routing between different Autonomous Systems across the internet.
  * *Security Perspective:* Highly targeted. Vulnerable to **BGP Hijacking** and **Route Leaks**, which allow attackers to intercept global traffic. Mitigation requires implementing **RPKI** (Resource Public Key Infrastructure) and **BGPsec**.

### 4. High Availability (HA) in Routing
* **HA Concepts (HSRP, VRRP, GLBP):** First-hop redundancy protocols that ensure continuous gateway availability during a hardware failure.
  * *Security Perspective:* Vulnerable to **ARP Spoofing** and **Virtual MAC Spoofing**. If left unauthenticated, an attacker can spoof the active virtual router, executing a highly effective Man-in-the-Middle (MITM) attack.

---

## 🌐 Part 2: Advanced Network Infrastructure (VoIP & SDN)

### 1. Unified Communication (UC) & Voice over IP (VoIP)
* Integration of voice, video, data, and collaboration tools over IP networks.
* *Security Perspective:* 
  * **SIP Flooding:** Attackers target Session Initiation Protocol (SIP) ports to trigger Denial of Service (DoS), crashing the corporate communication system.
  * **Eavesdropping:** If voice streams are unencrypted, attackers can use tools like **Wireshark** to capture packets and reconstruct private conversations. Implementation of **SRTP (Secure RTP)** and **TLS** is mandatory.

### 2. Software-Defined Networking (SDN)
* Centralized network architecture that decouples the Control Plane (intelligence) from the Data Plane (forwarding hardware).
* *Security Perspective:* 
  * Creates a **Single Point of Failure**. Compromising the centralized SDN controller grants an attacker absolute control over the entire network fabric.
  * Requires strict cryptographic security, token authorization, and **RBAC (Role-Based Access Control)** across all Northbound (application) and Southbound (infrastructure) APIs.

---

## ☁️ Part 3: Virtualization & Cloud Security

### 1. Hypervisors & Virtual Machine Monitors (VMM)
* Software layer that creates and runs Virtual Machines (VMs), categorized into Type-1 (Bare-metal) and Type-2 (Hosted).
* *Security Perspective:* The primary threat vector is **VM Escape**, where an attacker breaks out of a guest OS context to execute malicious code directly on the host hypervisor, compromising all other co-hosted VMs. Regular hypervisor patching and strict hardware-level isolation are vital.

### 2. Cloud Classifications & Architecture Types
* Cloud Deployment Models (Public, Private, Hybrid, Community) and Service Models (IaaS, PaaS, SaaS).
* *Security Perspective:* 
  * Driven by the **Shared Responsibility Model**. Security failures often stem from consumer **Misconfigurations** (e.g., exposed AWS S3 Buckets, weak IAM policies) rather than cloud provider vulnerabilities.
  * Requires rigorous API security management and multi-tenant isolation monitoring.

---

## 💾 Part 4: Storage Area Networks (SAN) Technology

### 1. SAN Justification & Concepts
* A dedicated, high-speed network providing block-level network access to storage.
* *Security Perspective:* Storage networks contain the crown jewels (sensitive corporate data). To prevent unauthorized access, data breaches, and ransomware propagation, SAN fabrics must be physically or logically isolated from standard production LAN traffic.

### 2. SAN Technologies (FC, iSCSI, FCoE)
* Protocols utilized to transport storage traffic over networks (Fibre Channel, Internet Small Computer Systems Interface, Fibre Channel over Ethernet).
* *Security Perspective:* 
  * **iSCSI:** Transmits data over standard IP networks. If unencrypted, it is susceptible to network sniffing. Requires **CHAP Authentication** and **IPsec** encryption tunnels.
  * **Fibre Channel (FC):** Vulnerable to **WWN (World Wide Name) Spoofing**. Securing the fabric mandates the enforcement of strict **Fabric Zoning** (preferably hard zoning) and **LUN Masking**.

---

## 🏗️ Part 5: Secure Network Planning & Configuration

### 1. Network Design & Segmentation
* The process of structuring and deploying a resilient, secure network infrastructure using a "Security-by-Design" philosophy.
* *Key Security Pillars:*
  * **Zero Trust Architecture (ZTA):** Moving away from perimeter defenses; every access request must be explicitly authenticated and authorized, regardless of its origin.
  * **Micro-Segmentation:** Utilizing VLANs, VRFs, and Next-Generation Firewalls (NGFW) to isolate sensitive assets (e.g., isolating a DMZ from the internal core database).
  * **Strict Access Control Lists (ACLs):** Implementing a default-deny posture on all routers and firewalls, opening only explicitly required ports and protocols.
