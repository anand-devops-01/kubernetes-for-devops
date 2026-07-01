# Namespaces in Kubernetes

## What is a Namespace?

A Namespace is a logical partition inside a Kubernetes cluster.

It allows multiple teams, applications, or environments to share the same cluster without interfering with each other.

---

# Why Use Namespaces?

Namespaces help in:

- Resource Isolation
- Multi-Tenant Clusters
- Environment Separation
- Better Resource Management

---

# Default Namespaces

Kubernetes creates these namespaces automatically:

- default
- kube-system
- kube-public
- kube-node-lease

---

# Create Namespace

```bash
kubectl create namespace dev
```

---

# List Namespaces

```bash
kubectl get namespaces
```

---

# Describe Namespace

```bash
kubectl describe namespace dev
```

---

# Delete Namespace

```bash
kubectl delete namespace dev
```

---

# Deploy Resources in a Namespace

```bash
kubectl apply -f deployment.yaml -n dev
```

---

# Set Default Namespace

```bash
kubectl config set-context --current --namespace=dev
```

---

# Advantages

- Isolation
- Security
- Resource Quotas
- Team Collaboration
- Environment Separation

---

# Real World Example

A company uses:

- dev
- testing
- staging
- production

Each environment runs inside its own Namespace.

---

# Interview Questions

### What is a Namespace?

A Namespace is a logical partition of a Kubernetes cluster.

### Why are Namespaces used?

To isolate applications and resources.

### Which Namespace is used by default?

default

### Which command lists all Namespaces?

```bash
kubectl get namespaces
```