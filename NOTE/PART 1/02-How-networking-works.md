# How a Network Works

## Overview

A network allows devices to communicate by sending and receiving data using networking protocols.

When we access a website, many processes happen between our device and the destination server.

Basic flow:

    Your Device
         ↓
    Wi-Fi / Switch
         ↓
       Router
         ↓
        ISP
         ↓
    Internet Routers
         ↓
    Destination Server
         ↓
      Response

---

## Example

Suppose we enter:

    https://example.com

into a web browser.

Our device needs to communicate with the server hosting that website.

The communication happens through several steps.

---

## Step 1 — Connect to a Network

First, the device must be connected to a network.

For example:

- Wi-Fi
- Ethernet

A home device usually connects to a local router.

Example:

    Laptop
       ↓
    Wi-Fi Router

---

## Step 2 — DNS Resolution

Humans usually use domain names such as:

    example.com

Computers communicate using IP addresses.

DNS (Domain Name System) translates a domain name into an IP address.

Simplified:

    example.com
         ↓
        DNS
         ↓
    IP Address

For example:

    example.com → 93.x.x.x

The actual IP address can vary.

---

## Step 3 — Creating Network Data

The application generates data that needs to be transmitted.

Different networking layers add information needed for communication.

A simplified model is:

    Application
        ↓
    Transport
        ↓
    Internet
        ↓
    Network Access

Each layer has a different responsibility.

---

## Step 4 — Data Is Sent as Packets

Large amounts of network data are transmitted in smaller units.

At the IP layer, these units are called packets.

Simplified:

    Data
     ↓
    Packet 1
    Packet 2
    Packet 3
     ↓
    Network

Each packet contains addressing information that helps the network deliver it toward its destination.

---

## Step 5 — Router Forwards the Packet

The packet reaches a router.

The router examines the destination IP address and uses its routing information to determine where to forward the packet.

Simplified:

    Packet
      ↓
    Router
      ↓
    Next Network

The router does not normally need to understand the application's full content in order to perform basic IP forwarding.

---

## Step 6 — Multiple Routers May Be Involved

A packet may travel through multiple routers before reaching its destination.

Example:

    Your Device
         ↓
       Router A
         ↓
       Router B
         ↓
       Router C
         ↓
       Router D
         ↓
       Server

The exact path can vary depending on network routing conditions.

---

## Step 7 — Destination Server Receives the Request

Eventually, the packets reach the destination network and server.

The server processes the request.

For a web request, the server may return:

- HTML
- CSS
- JavaScript
- Images
- API data

---

## Step 8 — Response Travels Back

The server sends a response back toward the client.

Simplified:

    Server
      ↓
    Routers
      ↓
    ISP
      ↓
    Home Router
      ↓
    Your Device

The response may not necessarily follow exactly the same physical path as the original traffic.

---

# Important Concepts

## IP Address

An IP address is used for addressing devices/interfaces at the IP layer.

Example:

    192.168.1.10

---

## Router

A router connects different networks and forwards IP packets toward their destinations.

---

## Packet

A packet is a unit of data transmitted at the IP/network layer.

It contains information needed to help deliver the data across networks.

---

## Protocol

Protocols define rules for communication.

Examples:

- IP
- TCP
- UDP
- DNS
- HTTP
- HTTPS

---

# Simple Real-World Example

When you open a website:

    Browser
       ↓
    DNS lookup
       ↓
    Destination IP
       ↓
    Packets created
       ↓
    Router
       ↓
    ISP
       ↓
    Internet
       ↓
    Destination Server
       ↓
    Response
       ↓
    Browser displays the website

---

# How This Relates to Cybersecurity

Understanding network communication is essential for cybersecurity.

Attackers also communicate through networks.

For example, an attacker may:

- Scan IP addresses
- Scan ports
- Send malicious packets
- Intercept traffic
- Exploit network services
- Communicate with a compromised server
- Perform denial-of-service attacks

Defenders therefore need to understand normal network behavior before identifying abnormal behavior.

---

# Key Takeaway

A network works by allowing devices to exchange data using standardized protocols.

In a typical Internet communication:

    Device
      ↓
    Network
      ↓
    Router
      ↓
    ISP
      ↓
    Internet
      ↓
    Server
      ↓
    Response

Routers forward packets based on network addressing and routing information, allowing communication between different networks.
