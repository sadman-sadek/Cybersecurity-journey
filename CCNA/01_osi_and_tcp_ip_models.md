# CCNA Notes: OSI Model, TCP/IP Model, and Encapsulation

This note covers the core concepts from **NetworkChuck CCNA Episodes 2, 3, and 4**, focusing on network models, layers, TCP vs UDP, common ports, and data encapsulation.

---

## 🌐 OSI Model vs. TCP/IP Model (EP 2 & EP 3)

Network models help us understand how data travels across a network. While the **OSI Model** is the theoretical standard, the **TCP/IP Model** is what the internet actually uses.

### The 7 Layers of the OSI Model
To remember the layers easily, use these classic mnemonics:
*   **Top-Down (Layer 7 to 1):** "**A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing"
*   **Bottom-Up (Layer 1 to 7):** "**P**lease **D**o **N**ot **T**hrow **S**ausage **P**izza **A**way"

| Layer Number | Layer Name | Description / Protocol Examples |
| :---: | --- | --- |
| **7** | **Application** | Where the user interacts with the network (HTTP, HTTPS, FTP, SSH) |
| **6** | **Presentation** | Data formatting, encryption, and compression (SSL/TLS, JPEG, ASCII) |
| **5** | **Session** | Establishes, manages, and terminates connections between applications |
| **4** | **Transport** | Manages end-to-end delivery and error-checking (TCP, UDP) |
| **3** | **Network** | Handles logical addressing and routing across networks (IP, ICMP, Routers) |
| **2** | **Data Link** | Handles physical addressing and local media access (MAC Addresses, Switches) |
| **1** | **Physical** | Transmits raw bit streams over physical media (Cables, Fiber, Wi-Fi, Bits) |

### The 5-Layer TCP/IP Model
Modern networking simplifies the top three OSI layers into a single Application layer:
1.  **Application** (OSI Layers 5, 6, 7 combined)
2.  **Transport** (OSI Layer 4)
3.  **Network / Internet** (OSI Layer 3)
4.  **Data Link** (OSI Layer 2)
5.  **Physical** (OSI Layer 1)

---

## ⚡ Transport Layer: TCP vs. UDP (EP 4)

Layer 4 (Transport) uses two main protocols to move data:

| Feature | TCP (Transmission Control Protocol) | UDP (User Datagram Protocol) |
| :--- | :--- | :--- |
| **Reliability** | **Reliable** (Guarantees delivery via 3-way handshake) | **Unreliable** (Best-effort delivery, no handshake) |
| **Speed** | Slower (Due to error checking and overhead) | **Faster** (No overhead, fire-and-forget) |
| **Usage** | Web browsing (HTTP/S), Email, File transfers | Live streaming, VoIP, Online gaming, DNS |

---

## 🔒 Common Web Ports
*   **Port 80:** HTTP (Unencrypted / Clear text)
*   **Port 443:** HTTPS (Encrypted / Secure via SSL/TLS)

---

## 📦 How Data Travels: Encapsulation (EP 4)

When you send a request (e.g., loading an HTTPS website), the data moves **down** the layers from **Layer 7 to Layer 1**. At each layer, new control information (headers) is added. This process is called **Encapsulation**.

### The Encapsulation Journey (Data Protocol Units - PDUs)
1.  **Application Layer (Data):** You request a secure webpage using **HTTPS (Port 443)**.
2.  **Transport Layer (Segment):** The data is chopped into segments. A **TCP Header** is added containing the Source Port and Destination Port (443).
3.  **Network Layer (Packet):** An **IP Header** is added containing the Source IP and Destination IP address.
4.  **Data Link Layer (Frame):** A **Layer 2 Frame Header and Trailer** are added containing the Source and Destination **MAC addresses**.
5.  **Physical Layer (Bits):** The entire frame is converted into raw binary **1s and 0s** (electrical impulses, light beams, or radio waves) and sent across the wire.

*Note: When the receiving device gets the bits, it strips the headers layer-by-layer going **up** from Layer 1 to Layer 7. This reverse process is called **Decapsulation**.*
