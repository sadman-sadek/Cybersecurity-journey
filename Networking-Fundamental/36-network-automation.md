# 36 — Network Automation

Automation means turning repeated network reasoning into repeatable code.

## Automation ladder

```text
Command
↓
Script
↓
Structured output
↓
API
↓
Configuration management
↓
Continuous validation
```

## Examples

Automate:

- device inventory
- interface checks
- route snapshots
- DNS validation
- configuration backups
- firewall-rule audits
- certificate expiry checks
- service availability

## Good automation

Should be:

- repeatable
- logged
- idempotent where appropriate
- testable
- least-privileged
- safe by default

## Project

Build:

```text
network-audit/
├── inventory.yaml
├── scanner.py
├── checks/
├── reports/
└── README.md
```

The report should identify:

- reachable hosts
- open expected services
- unexpected services
- DNS mismatches
- missing security controls
