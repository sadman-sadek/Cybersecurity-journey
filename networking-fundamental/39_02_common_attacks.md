# Common Network Attacks — Learn the Mechanism

Study attacks only after understanding the normal protocol.

## ARP spoofing

Abuses trust in ARP mappings to redirect local traffic.

## DNS poisoning/spoofing

Attempts to cause incorrect name resolution.

## DHCP attacks

Can attempt to provide malicious configuration or exhaust available leases.

## MAC flooding

Attempts to overload switch MAC-learning behavior.

## VLAN-related attacks

Misconfiguration or protocol abuse can weaken intended segmentation.

## DoS/DDoS

Attempts to make services unavailable through resource exhaustion.

## MITM

An attacker positions themselves so traffic passes through them, enabling interception or manipulation depending on encryption and circumstances.

## Defensive mindset

For every attack ask:

1. What normal protocol assumption is abused?
2. Where does the attack occur?
3. What evidence would appear?
4. What control can reduce it?
