# How to Study Networking Without Drowning in Theory

Networking is a **systems subject**. Memorization alone produces fragile knowledge.

## The 7-step loop

### 1. Learn one concept

Example: ARP.

### 2. Draw it

Host A → Switch → Host B.

Write:

- source IP
- destination IP
- source MAC
- destination MAC

### 3. Predict

Ask:

> What happens if Host A knows B's IP but not B's MAC?

### 4. Observe

Use a packet capture or simulator.

### 5. Break it

Change the IP, gateway, VLAN, route, DNS setting, or service.

### 6. Explain the failure

Do not immediately search for the answer.

### 7. Repeat from memory

If you cannot reconstruct it, the concept is not stable yet.

## Rule: understand before memorizing

Memorize facts that are useful operationally:

- common ports
- protocol names
- address ranges
- subnet powers of two

But first understand **why the system needs the fact**.

## The packet-story method

For any communication, tell the story:

1. Application creates data.
2. Transport chooses TCP/UDP and a port.
3. IP adds source/destination IP.
4. Link layer adds source/destination MAC.
5. Bits travel over the medium.
6. Receiver decapsulates.
7. The application receives the data.

Then ask what changes at each hop.
