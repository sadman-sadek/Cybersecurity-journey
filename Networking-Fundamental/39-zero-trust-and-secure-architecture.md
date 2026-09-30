# 39 — Zero Trust and Secure Architecture

Zero Trust is a security architecture principle, not a single product.

Core mindset:

```text
Do not grant broad trust merely because traffic is "internal."
```

## Architecture questions

For every request:

```text
Who?
What device/workload?
What resource?
Why?
What policy?
What context?
What logging?
How much access?
For how long?
```

## Compare architectures

### Flat

```text
Users ─ Servers ─ Admin
     \___________/
```

### Segmented

```text
Users → Firewall → App → Database
Admin → Firewall → Management
```

### Identity-aware

```text
User/device identity
       ↓
Policy engine
       ↓
Specific application
```

## Exercise

Take a fictional company and design:

- user network
- server network
- management network
- guest network
- security monitoring
- Internet edge

Then document allowed flows and denied flows.
