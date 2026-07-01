# Labels and Selectors in Kubernetes

## What are Labels?

Labels are key-value pairs attached to Kubernetes objects such as Pods, Deployments, and Services.

They help identify, organize, and manage resources.

Example:

```yaml
labels:
  app: nginx
  env: production
```

---

# Why Labels?

Labels help in:

- Resource Identification
- Resource Grouping
- Service Discovery
- Deployment Management
- Filtering Resources

---

# What are Selectors?

Selectors are used to find Kubernetes objects based on Labels.

Example:

```yaml
selector:
  app: nginx
```

This selector matches all Pods having:

```yaml
labels:
  app: nginx
```

---

# Types of Selectors

## Equality-Based Selector

```bash
kubectl get pods -l app=nginx
```

Example:

```
app=nginx
env=prod
```

---

## Set-Based Selector

```bash
kubectl get pods -l 'env in (dev,prod)'
```

Examples:

```
env in (dev,prod)

tier notin (frontend)

app
```

---

# Add Label

```bash
kubectl label pod nginx-pod env=production
```

---

# Show Labels

```bash
kubectl get pods --show-labels
```

---

# Filter Pods

```bash
kubectl get pods -l app=nginx
```

---

# Remove Label

```bash
kubectl label pod nginx-pod env-
```

---

# Real World Example

Frontend Pods:

```yaml
labels:
  app: frontend
```

Backend Pods:

```yaml
labels:
  app: backend
```

Frontend Service only sends traffic to Pods having:

```yaml
selector:
  app: frontend
```

---

# Advantages

- Easy Resource Management
- Service Discovery
- Filtering Resources
- Organized Cluster
- Supports Scaling

---

# Interview Questions

### What is a Label?

A Label is a key-value pair attached to Kubernetes objects.

---

### What is a Selector?

A Selector identifies Kubernetes resources using Labels.

---

### Can a Pod have multiple Labels?

Yes.

---

### Which Kubernetes objects use Labels?

Pods, Deployments, ReplicaSets, Services, Namespaces and more.

---

### Which command shows Labels?

```bash
kubectl get pods --show-labels
```