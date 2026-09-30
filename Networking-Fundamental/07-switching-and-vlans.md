# 07 — Switching and VLANs

## Switch forwarding

A switch maintains a MAC/CAM table:

```text
MAC                Port
AA:AA:AA:AA:AA:AA  1
BB:BB:BB:BB:BB:BB  7
```

If destination is known:

```text
forward only to matching port
```

If unknown/broadcast:

```text
flood within the relevant Layer-2 domain
```

## VLAN

A VLAN creates logical Layer-2 separation.

Example:

```text
VLAN 10 — Users
VLAN 20 — Servers
VLAN 30 — Management
```

Hosts in different VLANs need Layer-3 routing to communicate.

## Access vs trunk

Access port:

```text
endpoint ←→ switch
one VLAN
```

Trunk:

```text
switch ←→ switch/router/firewall
multiple VLANs
```

802.1Q tagging identifies VLAN membership on tagged links.

## Lab idea

Build:

```text
PC1 ---+
       |
     Switch
       |
PC2 ---+
```

Create two VLANs and observe:

1. same-VLAN communication
2. cross-VLAN failure
3. routing between VLANs
4. firewall policy between VLANs

## Security questions

- Which VLAN contains management?
- Can users reach management?
- Is the trunk restricted?
- Are unused ports disabled?
- What happens if a malicious device appears?
