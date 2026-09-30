# 1 — Networking Big Picture

## Network
A network connects devices so they can exchange data and share resources.

### Devices
- Endpoint: PC, phone, server, printer, camera, IoT.
- Switch: Layer 2 forwarding inside a LAN.
- Router: Layer 3 forwarding between networks.
- AP: wireless-to-network connectivity.
- Firewall: traffic-security policy.
- Load balancer: distributes service traffic.
- Modem/ONT: ISP access interface.

## Network types
- PAN: personal area.
- LAN: local area.
- WLAN: wireless LAN.
- CAN: campus.
- MAN: metropolitan.
- WAN: geographically separated networks.
- SAN: storage network.

## Architectures
- Client-server: clients consume centralized services.
- Peer-to-peer: peers can provide services directly.
- Two-tier/three-tier: hierarchical enterprise designs.
- Spine-leaf: common data-center architecture optimized for east-west traffic.
- SOHO: integrated router/switch/AP/firewall style equipment.

## Network planes
- Data plane: forwards traffic.
- Control plane: calculates/controls forwarding behavior.
- Management plane: configuration and monitoring.

## Performance
- Bandwidth = capacity.
- Throughput = actual useful transfer.
- Latency = delay.
- Jitter = variation in delay.
- Packet loss = packets not successfully delivered.

## Physical vs logical
Physical topology describes actual connections. Logical topology describes how traffic/segments behave.

## Quick recall
`MAC → local link`
`IP → network-to-network`
`Port → application endpoint`
