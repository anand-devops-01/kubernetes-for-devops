# Pods in Kubernetes

## What is a Pod?

A Pod is the smallest deployable unit in Kubernetes.

A Pod can contain:

- One container (most common)
- Multiple containers (sidecar pattern)

Pods share:

- Network
- IP Address
- Storage (Volumes)

---

# Why Pods?

Instead of managing containers directly, Kubernetes manages Pods.

Benefits:

- Easy deployment
- Scaling
- Self-healing
- Networking
- Storage sharing

---

# Pod Lifecycle

1. Pending
2. Running
3. Succeeded
4. Failed
5. Unknown

---

# Create a Pod

```bash
kubectl apply -f pod.yaml
```

---

# List Pods

```bash
kubectl get pods
```

---

# Describe Pod

```bash
kubectl describe pod nginx-pod
```

---

# Delete Pod

```bash
kubectl delete pod nginx-pod
```

---

# Get Pod Logs

```bash
kubectl logs nginx-pod
```

---

# Execute Inside Pod

```bash
kubectl exec -it nginx-pod -- /bin/bash
```

---

# Advantages

- Lightweight
- Fast deployment
- Shared networking
- Easy scaling
- High availability

---

# Real World Example

A simple Nginx web server running inside a Kubernetes Pod.

---

# Interview Questions

### What is a Pod?

The smallest deployable unit in Kubernetes.

### Can a Pod have multiple containers?

Yes.

### Does every Pod have its own IP?

Yes.

### Which command creates a Pod?

```bash
kubectl apply -f pod.yaml
```