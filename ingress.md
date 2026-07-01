# Ingress in Kubernetes

## What is Ingress?

Ingress is a Kubernetes API object that manages external HTTP and HTTPS access to services inside a cluster.

Instead of exposing every Service using NodePort or LoadBalancer, Ingress provides a single entry point.

---

# Why Ingress?

Ingress provides:

- HTTP Routing
- HTTPS Support
- SSL Termination
- Host-Based Routing
- Path-Based Routing
- Load Balancing

---

# Architecture

```
Internet
    │
    ▼
Ingress Controller
    │
    ▼
Ingress
    │
 ┌──┴─────────────┐
 │                │
 ▼                ▼
Service A     Service B
 │                │
 ▼                ▼
Pods          Pods
```

---

# Features

- Single Entry Point
- SSL/TLS
- URL Routing
- Virtual Hosting
- Load Balancing

---

# Create Ingress

```bash
kubectl apply -f ingress.yaml
```

---

# List Ingress

```bash
kubectl get ingress
```

---

# Describe Ingress

```bash
kubectl describe ingress app-ingress
```

---

# Advantages

- Easy Routing
- HTTPS Support
- Cost Effective
- Better Traffic Management

---

# Real World Example

```
example.com
        │
        ├── /api  → Backend Service
        ├── /web  → Frontend Service
        └── /admin → Admin Service
```

---

# Interview Questions

### What is Ingress?

Ingress routes external HTTP/HTTPS traffic to Kubernetes Services.

### Does Ingress expose Pods directly?

No. It exposes Services.

### Is an Ingress Controller required?

Yes.

### Name popular Ingress Controllers.

- NGINX Ingress Controller
- Traefik
- HAProxy
- AWS ALB Controller