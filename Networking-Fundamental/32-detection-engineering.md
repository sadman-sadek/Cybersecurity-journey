# 32 — Detection Engineering

A detection is a testable hypothesis.

Bad:

```text
Detect hackers.
```

Better:

```text
Detect unusually high outbound TCP connection rates from a workstation.
```

## Detection lifecycle

```text
Threat hypothesis
↓
Observable data
↓
Feature
↓
Rule/model
↓
Alert
↓
Validation
↓
Tuning
↓
Response
```

## Example

Hypothesis:

```text
A compromised workstation may scan many internal hosts.
```

Potential signals:

- many destination IPs
- many destination ports
- short connection attempts
- high SYN-to-completion ratio

Possible false positives:

- vulnerability scanners
- monitoring tools
- inventory systems
- administrators

## Exercise

Design five detections:

1. suspicious DNS volume
2. internal port scanning
3. repeated SSH failures
4. unexpected management access
5. unusual outbound connection burst

For each include:

- data source
- query logic
- false positives
- severity rationale
- validation lab
