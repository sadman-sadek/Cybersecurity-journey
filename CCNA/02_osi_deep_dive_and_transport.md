# CCNA Notes: OSI Deep Dive, Important Ports, and TCP Handshake

This note covers detailed functionalities of the upper OSI layers, essential network ports, and the mechanism of the TCP 3-Way Handshake based on **NetworkChuck CCNA Episode 5**.

---

## 🎨 Presentation & Session Layers (Layer 6 & Layer 5)

### Layer 6: Presentation Layer
Handles how data is formatted, secured, and structured for the application layer.
*   **Data Formatting:** Defines file extensions and structures (e.g., HTML, XML, JSON, `myfile.pdf`).
*   **Encryption & Security:** Handles encryption protocols like **SSL/TLS** to secure data in transit.

### Layer 5: Session Layer
Manages the establishment, maintenance, and termination of sessions between applications.
*   **Protocols involved:**
    *   **L2TP** (Layer 2 Tunneling Protocol)
    *   **RTCP** (RTP Control Protocol)
    *   **H.245** (Control channel protocol for multimedia communication)
    *   **SOCKS** (Socket Secure protocol)

---

## 🏎️ Transport Layer: TCP Connection & Handshake

As established, **TCP** is reliable and connection-oriented, whereas **UDP** is faster but connectionless. 

### The TCP Three-Way Handshake
Before TCP sends any actual data (like streaming a YouTube video), it establishes a verified connection using a **Three-Way Handshake**:

```text
  Client (You)                          Server (YouTube)

       |                                       |
       | ------------ 1. SYN ------------->    |  (Synchronize)
       |                                       |
       | <--------- 2. SYN-ACK ------------    |  (Synchronize-Acknowledgment)
       |                                       |
       | ------------ 3. ACK ------------->    |  (Acknowledgment)
       |                                       |
```

1.  **SYN:** The client sends a synchronize packet to request a connection.
2.  **SYN-ACK:** The server responds, acknowledging the request and asking to synchronize back.
3.  **ACK:** The client acknowledges the server's response. The reliable connection is now established!

---

## 🔌 Important Network Ports to Remember

Ports direct network traffic to the correct application on a device.

| Port Number | Protocol | Description | Security Status |
| :---: | :---: | --- | :--- |
| **20 / 21** | **FTP** | File Transfer Protocol (Data / Control) | ❌ **Unsafe** (Plaintext) |
| **22** | **SSH** | Secure Shell (Encrypted remote login) |  **Safe** |
| **3389** | **RDP** | Remote Desktop Protocol | Used for GUI remote access |

### Port Types
*   **Important / Well-Known Ports:** Standard system ports ranging from **0 to 1023** (e.g., HTTP 80, HTTPS 443, SSH 22).
*   **Ephemeral Ports:** Temporary, short-lived ports automatically assigned by the client OS for outgoing connections (typically ranging from **49152 to 65535**).
*
