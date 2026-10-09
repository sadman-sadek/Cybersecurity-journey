# EP-17: Network Subnetting & CIDR

This section covers the core concepts of Subnetting, Classless Inter-Domain Routing (CIDR), bit-borrowing math, and reverse subnet analysis.

---

## 1. Fundamentals of Subnetting & CIDR

Subnetting is the practice of dividing a large network into smaller, more efficient sub-networks (subnets). **CIDR (Classless Inter-Domain Routing)** replaces the traditional classful addressing system with a flexible system using a prefix length (e.g., `/24`, `/26`).

### Bit Value Chart (The Magic Number Table)
To calculate subnets quickly, memorize the positional values of an 8-bit octet:

| Bit Position | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Decimal Value** | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
| **Cumulative Value** | 128 | 192 | 224 | 240 | 248 | 252 | 254 | 255 |

---

## 2. Subnet Design Methodology

When customized subnets are required, follow these four foundational steps:

1. **Determine Required Bits:** Use formulas to find how many bits must be borrowed or kept.
   * **For Subnets:** \(2^n \geq \text{Required Subnets}\) (where \(n\) is borrowed network bits).
   * **For Hosts:** \(2^h - 2 \geq \text{Required Hosts}\) (where \(h\) is remaining host bits).
2. **Borrow ("Hack") the Bits:** Convert the custom bits from `0` to `1` in the subnet mask.
3. **Find the Increment (Block Size):** Locate the value of the last borrowed bit (the lowest active bit in the modified octet).
4. **Create the Network Ranges:** Start at `.0` and add the increment to list your subnets.

---

## 3. Subnetting Examples

### Example A: Subnetting for 4 Networks
If you start with a standard `/24` network (e.g., `192.168.1.0/24`) and need **4 subnets**:
* **Bits required:** \(2^2 = 4\), so we borrow **2 bits** from the host portion.
* **New Prefix Length:** \(/24 + 2 = /26\)
* **Binary Mask Changes to:** `11111111.11111111.11111111.11000000` (\(\text{Decimal} = 255.255.255.192\)).
* **Increment Value:** The value of the second bit from the left is **64**.

#### Subnet Block Breakdowns

| Subnet Number | Network Address | Usable Host Range | Broadcast Address |
| :---: | :--- | :--- | :--- |
| **Subnet 1** | `192.168.1.0` | `192.168.1.1` – `192.168.1.62` | `192.168.1.63` |
| **Subnet 2** | `192.168.1.64` | `192.168.1.65` – `192.168.1.126` | `192.168.1.127` |
| **Subnet 3** | `192.168.1.128` | `192.168.1.129` – `192.168.1.190` | `192.168.1.191` |
| **Subnet 4** | `192.168.1.192` | `192.168.1.193` – `192.168.1.254` | `192.168.1.255` |

---

### Example B: Allocating a Subnet for 40 Hosts
If you start with a standard network block `10.1.1.0/24` and need to accommodate a subnet with **40 usable hosts**:
* **Bits required:** Look at the bit chart. \(2^5 = 32\) (too small), \(2^6 = 64\) (holds 40 hosts). Thus, we must keep **6 host bits**.
* **Bits Borrowed:** \(8 - 6 = 2 \text{ bits}\) are borrowed for the subnet portion.
* **New Prefix Length:** \(/24 + 2 = /26\)
* **Subnet Mask:** `255.255.255.192`
* **Increment Value:** **64**

#### Resulting Network Allocations
* **Subnet 1:** `10.1.1.0` to `10.1.1.63`
* **Subnet 2:** `10.1.1.64` to `10.1.1.127`
* **Subnet 3:** `10.1.1.128` to `10.1.1.192`

---

## 4. Reverse Subnet Engineering

Reverse engineering allows you to take any random IP address paired with a subnet mask and find its exact home network boundaries.

### Scenario Analysis
* **Target IP Address:** `172.17.16.255`
* **Given Subnet Mask:** `255.255.240.0` (`/20`)

#### Step-by-Step Resolution
1. **Analyze the Binary Mask:**
   ```text
   255      . 255      . 240      . 0
   11111111 . 11111111 . 11110000 . 00000000
   ```
2. **Find the Interesting Octet:** The 3rd octet contains the boundary switch from network bits (`1`) to host bits (`0`).
3. **Find the Increment Value:** The lowest active network bit in the 3rd octet is in the 4th position, which equals **16**.
4. **Track the 3rd Octet Boundaries:**
   * Subnet 1: `172.17.0.0` – `172.17.15.255`
   * Subnet 2: `172.17.16.0` – `172.17.31.255`

#### Conclusion
The Target IP address `172.17.16.255` falls squarely into **Subnet 2** (`172.17.16.0/20`). It represents the last assignable host address or a broadcast boundary depending on its exact location.
