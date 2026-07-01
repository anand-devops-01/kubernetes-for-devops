# ReplicaSets in Kubernetes

## What is a ReplicaSet?

A ReplicaSet ensures that a specified number of Pod replicas are always running.

If a Pod crashes or is deleted, the ReplicaSet automatically creates a new Pod.

---

## Why Use ReplicaSets?

- High Availability
- Fault Tolerance
- Automatic Recovery
- Desired Number of Pods

---

## How ReplicaSet Works

ReplicaSet continuously monitors Pods.

If:

- Pods < Desired Replicas → Creates new Pods
- Pods > Desired Replicas → Deletes extra Pods

---

## Create ReplicaSet

```bash
kubectl apply -f replicaset.yaml
```

---

## List ReplicaSets

```bash
kubectl get rs
```

---

## Describe ReplicaSet

```bash
kubectl describe rs nginx-rs
```

---

## Delete ReplicaSet

```bash
kubectl delete rs nginx-rs
```

---

## Scale ReplicaSet

```bash
kubectl scale rs nginx-rs --replicas=5
```

---

## Advantages

- Self Healing
- High Availability
- Automatic Scaling
- Easy Pod Management

---

## Real World Example

An e-commerce website always requires 3 Nginx Pods running.

If one Pod crashes, ReplicaSet immediately creates another Pod.

---

# Interview Questions

### What is a ReplicaSet?

A ReplicaSet maintains the desired number of Pod replicas.

### Does ReplicaSet perform rolling updates?

No.

### Which Kubernetes object replaced ReplicaSet in production?

Deployment.

### Which command lists ReplicaSets?

```bash
kubectl get rs
```