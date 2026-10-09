# EP-11: How Ethernet Cables Work

This section covers the fundamentals of Ethernet cabling, media types, twisted-pair technology, speed standards, and pinout wiring standards (T568A/T568B).

---

## 1. Cloud & Virtualization Overview
* **Hybrid Cloud:** A computing environment that combines a private cloud (on-premises infrastructure) with a public cloud.
* **VMware:** A leading virtualization and cloud computing platform provider.

---

## 2. Ethernet Cable Basics
Ethernet cables transmit data packets between devices using copper wiring. 

### Common Copper Cable Types
* **UTP (Unshielded Twisted Pair):** Highly flexible, commonly used in indoor LANs, lacks shielding against interference.
* **STP (Shielded Twisted Pair):** Includes protective shielding to minimize electromagnetic interference (EMI).
* **EMT (Electrical Metallic Tubing):** Metal conduits used to run cables safely through structures.

### Physical Core & Configuration
* **Copper Wire Core:** Used for electrical signal transmission.
* **Why are the wires twisted?** Wires are twisted together in pairs to reduce **crosstalk** and electromagnetic interference (EMI).
* **Historical Categories:**
  * **Cat 3:** Older wiring, used for legacy networks.
  * **Cat 5:** Standard for 100 Mbps Fast Ethernet networks.

---

## 3. Ethernet Speed Standards
Ethernet standards dictate the data transfer rate and distance capabilities over twisted-pair copper cabling.

| Standard Name | Speed (Data Rate) | Media Type |
| :--- | :--- | :--- |
| **10Base-T** | 10 Mbps | Twisted Pair (Copper) |
| **100Base-T** | 100 Mbps | Twisted Pair (Copper) |
| **10G-Base-T** | 10 Gbps | Cat 6A / Twisted Pair |

---

## 4. Pin Configuration & Wiring Logic

### 10Base-T / 100Base-T Core Wiring
For a standard **10Base-T** and **100Base-T** network connection, only **4 wires (2 pairs)** out of the 8 pins are actively used for communication:
* **Send (Transmit) Pins:** Pin 1 & Pin 2
* **Receive Pins:** Pin 3 & Pin 6

```text
[PC]                               [Switch]
 Pin 1 (White-Orange) -------------> Pin 1 (Send)
 Pin 2 (Orange)       -------------> Pin 2 (Send)
 Pin 3 (White-Green)  <------------- Pin 3 (Receive)
 Pin 6 (Green)        <------------- Pin 6 (Receive)
```

### Crossover Cable (Switch-to-Switch)
When connecting similar devices directly (like a Switch to a Switch), the transmit pairs must be crossed over to the receive pairs on the other side. This enables them to talk properly:

```text
Switch 1 Pins:   1   2   3   4   5   6   7   8

                 |   |   |   |   |   |   |   |
                 X   X   X   |   |   X   |   |

                 |   |   |   |   |   |   |   |
Switch 2 Pins:   3   6   1   4   5   2   7   8
```
* *Note: **Pin 1** crosses to **Pin 3**, and **Pin 2** crosses to **Pin 6**.*

---

## 5. Wiring Standards (T568A vs T568B)

### T568B Color Sequence (Industry Standard)
The full 8-wire sequential color code order for a standard **T568B** termination is:

| Pin Number | Wire Color |
| :---: | :--- |
| **1** | White-Orange |
| **2** | Orange |
| **3** | White-Green |
| **4** | Blue |
| **5** | White-Blue |
| **6** | Green |
| **7** | White-Brown |
| **8** | Brown |

### T568A Standard
An alternative layout primarily used in residential installations or older infrastructure where the Orange and Green pairs are swapped.

---

## 6. Modern Ethernet Technology
* **Auto-MDIX (Automatic Medium-Dependent Interface Crossover):** A modern feature on network interfaces that automatically detects the required cable connection type (straight-through or crossover) and configures the connection automatically. This eliminates the manual need for crossover cables between switches.
