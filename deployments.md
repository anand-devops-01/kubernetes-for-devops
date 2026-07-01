# Deployments in Kubernetes

## What is a Deployment?

A Deployment is a Kubernetes object used to manage Pods and ReplicaSets.

It provides declarative updates for applications and ensures the desired number of Pods are always running.

---

# Why Deployments?

Deployments provide:

- Rolling Updates
- Rollbacks
- Self Healing
- Scaling
- Zero Downtime Deployment

---

# Deployment Architecture

```
Deployment
      │
      ▼
ReplicaSet
      │
      ▼
Pods
```

---

# Create Deployment

```bash
kubectl apply -f deployment.yaml
```

---

# List Deployments

```bash
kubectl get deployments
```

---

# Describe Deployment

```bash
kubectl describe deployment nginx-deployment
```

---

# Scale Deployment

```bash
kubectl scale deployment nginx-deployment --replicas=5
```

---

# Update Deployment

```bash
kubectl set image deployment/nginx-deployment nginx=nginx:1.27
```

---

# Rollback Deployment

```bash
kubectl rollout undo deployment nginx-deployment
```

---

# Deployment Strategy

## Rolling Update

Updates Pods one by one without downtime.

## Recreate

Deletes old Pods first, then creates new Pods.

---

# Advantages

- Zero Downtime
- Easy Rollback
- Auto Scaling
- Self Healing
- Production Ready

---

# Real World Example

Updating an Nginx application from version 1.26 to 1.27 without affecting users.

---

# Interview Questions

### What is a Deployment?

A Deployment manages ReplicaSets and Pods.

### Can Deployment rollback?

Yes.

### Which strategy is used by default?

Rolling Update.

### Which command rolls back a Deployment?

```bash
kubectl rollout undo deployment nginx-deployment
```