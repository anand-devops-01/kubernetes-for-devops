# Resource Limits in Kubernetes

## What are Resource Limits?

Resource Limits control how much CPU and memory a container can use.

They help prevent one application from consuming all cluster resources.

---

# Why Resource Limits?

Without limits:

- One Pod can consume all CPU.
- One Pod can consume all Memory.
- Other applications may crash.

Resource Limits ensure fair resource usage.

---

# Resource Requests

A Request defines the minimum resources required by a container.

Example:

```yaml
resources:
  requests:
    cpu: "250m"
    memory: "256Mi"
```

---

# Resource Limits

A Limit defines the maximum resources a container can consume.

Example:

```yaml
resources:
  limits:
    cpu: "500m"
    memory: "512Mi"
```

---

# CPU Units

| Value | Meaning |
|--------|---------|
| 1000m | 1 CPU |
| 500m | 0.5 CPU |
| 250m | 0.25 CPU |

---

# Memory Units

| Value | Meaning |
|--------|---------|
| Mi | Mebibytes |
| Gi | Gibibytes |

Examples:

- 256Mi
- 512Mi
- 1Gi

---

# View Resource Usage

```bash
kubectl top pods
```

```bash
kubectl top nodes
```

---

# Advantages

- Prevents Resource Starvation
- Better Cluster Stability
- Fair Resource Allocation
- Improved Performance

---

# Real World Example

A production web application:

- Request: 250m CPU, 256Mi Memory
- Limit: 500m CPU, 512Mi Memory

---

# Interview Questions

### What is a Resource Request?

Minimum resources required by a container.

### What is a Resource Limit?

Maximum resources a container can use.

### Which command shows Pod resource usage?

```bash
kubectl top pods
```

### Why are Resource Limits important?

To prevent a single application from consuming all cluster resources.