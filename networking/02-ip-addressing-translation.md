# IP Addressing & Address Translation

This file explains how devices are identified on a network and how private addresses communicate with the public internet.

---

## 1. IP Address Assignment
* **DHCP (Dynamic Host Configuration Protocol):** 
  * A network protocol that automatically assigns IP addresses, subnet masks, gateways, and DNS details to devices when they connect to the network.
* **Static IP:** 
  * A permanent IP address manually assigned to a device. It does not change over time (commonly used for servers, printers).
* **Dynamic IP:** 
  * A temporary IP address assigned automatically by a DHCP server. It changes periodically or every time the device reconnects.

---

## 2. NAT & PAT (Network Address Translation)
Used to conserve IPv4 addresses by allowing private local networks to use a single or few public IP addresses.

* **NAT (Network Address Translation):**
  * **Static NAT:** Maps a single private IP address to a single public IP address permanently (1-to-1 mapping).
  * **Dynamic NAT:** Maps a private IP address to a pool of available public IP addresses on a first-come, first-served basis.
* **PAT (Port Address Translation / NAT Overload):**
  * Maps multiple private IP addresses to a *single* public IP address by using unique source port numbers for each connection. This is what most home routers use.
