# 01 — How to Use This Repository

## The 60-minute study cycle

### 0–10 min — Mental model

Draw the concept.

Example:

```text
Laptop
  |
  | Ethernet frame
  v
Switch
  |
  | IP packet
  v
Router
  |
  | NAT + new L2 frame
  v
Internet
```

### 10–25 min — Build

Run commands or configure a lab.

### 25–40 min — Observe

Capture traffic.

### 40–50 min — Break

Intentionally introduce one fault.

### 50–60 min — Explain

Write:

```text
What I expected:
What actually happened:
What packet proved it:
Root cause:
Fix:
Security implication:
```

## The packet diary

Create a file such as:

`notes/packet-diary.md`

For each important capture:

```text
Capture:
Goal:
Host:
Source:
Destination:
Protocol:
Frame:
Packet:
Segment/datagram:
Important fields:
Expected behavior:
Observed behavior:
What surprised me:
Security relevance:
```

## Don't read linearly forever

A strong workflow is:

```text
Read 10%
→ Lab 40%
→ Capture 30%
→ Troubleshoot 15%
→ Summarize 5%
```

If you find yourself reading for an hour without touching a terminal, stop and build something.
