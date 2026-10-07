# CCNA Notes: Data Center Architecture & Spine-Leaf Topology

This note focuses on modern Data Center design alternatives, optimizing East-West traffic, and Next-Gen SDN architectures based on **NetworkChuck CCNA Episode 7**.

---

## 🏢 Data Center Architecture vs. Traditional Campus

Traditional campus networks are optimized for **North-South Traffic** (traffic moving out to the Internet or in from the outside). 

However, modern Data Centers experience massive amounts of **East-West Traffic** (traffic moving laterally between servers, virtual machines, and storage nodes within the data center itself). To handle this efficiently, data centers use a specialized layout.

---

## 🌴 Spine-Leaf Topology

The **Spine-Leaf design** ensures predictable, low-latency performance where every leaf switch is exactly one hop away from every other leaf switch.

```text
      [ Spine 1 ]           [ Spine 2 ]         <-- Spine Switches (Backbone)
       /    \    \           /    \    \
      /      \    \         /      \    \
 [ Leaf 1 ]  [ Leaf 2 ]  [ Leaf 3 ]  [ Leaf 4 ] <-- Leaf Switches (Edge)
   │    │      │    │      │    │      │    │
 [Servers]   [Devs]      [Storage]   [Compute]
```

### Core Architecture Rules:
1.  **Leaf Switches:** All end-nodes (servers, load balancers, firewalls, developers' endpoints) connect exclusively to Leaf switches.
2.  **Spine Switches:** Leaf switches connect to all Spine switches in a full mesh. 
3.  **No Direct Connections:** Spine switches *never* connect directly to other Spine switches, and Leaf switches *never* connect directly to other Leaf switches.

---

## 🕸️ Network Virtualization Terminology

*   **Underlay Network:** The physical infrastructure—the actual cables, physical switches, and routing protocols (like OSPF or IS-IS) running to ensure basic connectivity.
*   **Overlay Network:** A virtual network built on top of the underlay infrastructure (using encapsulation technologies like VXLAN) to dynamically route traffic regardless of physical location.
*   **ACI (Application Centric Infrastructure):** Cisco's Software-Defined Networking (SDN) architecture designed for data centers.
*   **API (Application Programming Interface):** Allows software tools to programmatically configure and automate the network infrastructure.
*   **EPG (Endpoint Groups):** A container managed in Cisco ACI that groups collection of endpoints (like VMs or servers) together logically for application policy enforcement.
*
