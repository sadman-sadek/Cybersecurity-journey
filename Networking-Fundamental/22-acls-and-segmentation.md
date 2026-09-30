# 22 — ACLs and Segmentation

## Segmentation

Segmentation limits communication paths.

Example:

```text
Users VLAN
   |
 Firewall
 /       \
Servers  Internet
 |
Management VLAN
```

## ACL thinking

An ACL is a set of rules evaluated according to platform-specific behavior.

A common conceptual pattern:

```text
ALLOW source A → destination B : TCP/443
DENY everything else
```

## Security design

Avoid:

```text
Everyone → Everything
```

Prefer:

```text
User → Web service : required ports
App → Database    : database port
Admin → Mgmt      : management protocol
Internet → User   : usually restricted
```

## Microsegmentation

Modern environments may apply policy closer to workloads rather than relying only on physical networks.

## Lab challenge

Create:

```text
VLAN 10 Users
VLAN 20 Servers
VLAN 30 Management
```

Requirements:

- Users can reach web service
- Users cannot reach management
- Web server can reach database
- Users cannot reach database directly
- Admin subnet can reach management

Document every rule and its rationale.
