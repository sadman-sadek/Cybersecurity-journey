# Follow a Packet

Scenario:

```text
Laptop → Home Router → ISP → Internet Server
```

Destination:

```text
https://example.com
```

Build the story.

### Step 1 — DNS

What IP address is returned?

### Step 2 — Local decision

Is the server local or remote?

### Step 3 — ARP/NDP

If remote, what local next-hop MAC is needed?

### Step 4 — Transport

TCP/443 or another transport?

### Step 5 — Routing

What next hop does the gateway choose?

### Step 6 — Encapsulation

What does the frame look like on each link?

### Step 7 — TLS

Can the secure session be established?

### Step 8 — HTTP

Does the application request succeed?

This single exercise connects most of the repository.
