# 30 — IDS, IPS and Network Security Monitoring

## IDS

Intrusion Detection System:

```text
observe → analyze → alert
```

## IPS

Intrusion Prevention System:

```text
observe → analyze → enforce/block
```

## NSM

Network Security Monitoring focuses on collecting useful network evidence.

Sources may include:

- packet captures
- DNS logs
- firewall logs
- proxy logs
- flow records
- IDS alerts
- authentication logs

## Signature vs behavior

Signature:

```text
match known pattern
```

Behavioral/anomaly-oriented:

```text
identify unusual behavior
```

Both have strengths and weaknesses.

## Example detection hypothesis

Suspicious outbound DNS:

```text
many unique subdomains
+
high entropy names
+
regular timing
+
large volume
```

Do not call this proof of tunneling.

It is a hypothesis requiring more evidence.

## Exercise

Create normal traffic and suspicious-looking traffic in a lab.

Compare:

- frequency
- destinations
- packet sizes
- DNS names
- timing
- connection counts
