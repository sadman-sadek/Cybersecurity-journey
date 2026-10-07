# Network Troubleshooting Method

Do not guess. Reduce the problem.

## The layered sequence

```text
Physical
  ↓
Link
  ↓
IP
  ↓
Transport
  ↓
Application
```

## Example: website does not work

### 1. Physical

Is the interface connected?

### 2. Link

Is the interface associated/up?

### 3. IP

Does the host have a valid address?

### 4. Gateway

Can it reach the gateway?

### 5. Routing

Can it reach the remote network?

### 6. DNS

Does the hostname resolve?

### 7. Transport

Can the required port be reached?

### 8. TLS/Application

Does the application protocol work?

## Evidence hierarchy

Prefer:

1. direct observation
2. packet capture
3. command output
4. logs
5. configuration
6. assumptions

The lower you stay in the evidence hierarchy, the less reliable your diagnosis becomes.
