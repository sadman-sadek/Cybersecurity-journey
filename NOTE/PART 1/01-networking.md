# Networking — Basic Concept

## What is Networking?

Networking is the process of connecting two or more devices so they can communicate and exchange data.

A network can connect devices such as:

- Computers
- Smartphones
- Servers
- Routers
- Printers
- IoT devices

The connected devices communicate using predefined rules called **network protocols**.

---

## Why Do We Need Networking?

Networking allows devices to:

- Share data
- Access the Internet
- Share resources
- Communicate with each other
- Access remote services
- Connect to servers

For example, when a phone connects to Wi-Fi, the phone becomes part of a network and can communicate with the router and other network devices.

---

## Basic Example

Imagine:

    Laptop ──┐
             │
    Phone ───┼──> Router ───> Internet
             │
    PC ──────┘

The router acts as a central device in this small local network.

The devices can communicate with the router, and the router can forward their traffic toward other networks.

---

## How Networking Works — Basic Mechanism

Suppose you open:

    https://example.com

The basic process is roughly:

1. Your device connects to a network.
2. Your device needs to find the destination server.
3. DNS can translate the domain name into an IP address.
4. Your device creates network data and sends it toward the destination.
5. Routers forward the traffic between networks.
6. The destination server receives the request.
7. The server sends a response back.
8. Your device receives and processes the response.

Simplified:

    Your Device
         ↓
       Router
         ↓
    ISP / Internet
         ↓
      Routers
         ↓
      Server
         ↓
      Response

---

## Important Networking Components

### 1. Client

A client is a device or application that requests a service.

Examples:

- Web browser
- Smartphone
- Laptop

### 2. Server

A server provides a service or resource to clients.

Examples:

- Web server
- File server
- DNS server
- Mail server

### 3. Router

A router connects different networks and forwards packets toward their destination.

### 4. Switch

A switch connects devices inside a local network and forwards Ethernet frames to the appropriate device.

### 5. IP Address

An IP address identifies a device/interface on an IP network.

Example:

    192.168.1.10

### 6. MAC Address

A MAC address is a hardware/interface-level address used for communication within local network technologies such as Ethernet.

---

## What is a Protocol?

A protocol is a set of rules that defines how devices communicate.

Examples:

- TCP
- IP
- HTTP
- HTTPS
- DNS
- SSH
- FTP

Different protocols handle different parts of communication.

---

## What is a Packet?

When data is sent over an IP network, it is divided into smaller units of data.

These are commonly referred to as packets at the network layer.

For example:

    Large Data
        ↓
    Packet 1
    Packet 2
    Packet 3
    Packet 4
        ↓
      Network
        ↓
    Destination

The packets can travel through multiple network devices before reaching the destination.

---

## Network Types

### LAN — Local Area Network

A network covering a small area.

Example:

- Home Wi-Fi
- School laboratory
- Office network

### WAN — Wide Area Network

A network covering a large geographical area.

The Internet is a huge interconnected system of networks.

---

## Networking and Cybersecurity

Networking is extremely important in cybersecurity because most attacks involve communication over a network.

A cybersecurity professional needs to understand:

- IP addresses
- Ports
- Protocols
- Packets
- Routers
- DNS
- TCP/IP
- HTTP/HTTPS
- Network traffic

For example, if an attacker sends malicious traffic to a server, understanding networking helps us understand:

    Who sent it?
    Where did it go?
    Which port was targeted?
    Which protocol was used?
    What data was transmitted?

---

## Key Idea

Networking is basically:

**Connecting devices + defining communication rules + moving data between them.**

A cybersecurity professional must understand how normal network communication works before understanding how attackers abuse it.
