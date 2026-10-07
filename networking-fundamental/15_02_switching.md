# Ethernet Switching

A switch learns which MAC addresses are reachable through which ports.

Conceptually:

```text
MAC Address       Port
AA:AA:AA...       1
BB:BB:BB...       7
CC:CC:CC...       12
```

This is commonly called a CAM/MAC address table.

## Learning

When a frame arrives, the switch can learn the **source MAC** on the incoming port.

## Forwarding

If the destination MAC is known, the switch forwards the frame toward that port.

If unknown, the frame may be flooded within the relevant Layer-2 domain.

## Critical idea

Switches do not normally make forwarding decisions using destination IP addresses.

Routers do.

## Lab question

Connect three hosts to a switch. Clear the MAC table if your simulator allows it. Generate traffic and observe the table changing.
