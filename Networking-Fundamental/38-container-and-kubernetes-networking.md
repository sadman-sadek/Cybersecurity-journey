# 38 — Container and Kubernetes Networking

Containers introduce another networking layer.

## Container basics

A container may have:

- virtual interface
- namespace
- bridge
- NAT
- published port

Conceptually:

```text
Host
 |
Bridge
 |--- container A
 |--- container B
```

## Kubernetes concepts

Learn:

- Pod IP
- Service
- ClusterIP
- NodePort
- LoadBalancer
- Ingress
- NetworkPolicy
- CNI

## Security

Understand:

- pod-to-pod communication
- namespace boundaries
- network policies
- service exposure
- ingress paths
- egress control

## Lab

Create two containers:

```text
frontend
backend
```

Allow frontend → backend.

Then introduce a policy preventing an unrelated container from reaching backend.

Observe the network path rather than only trusting the YAML.
