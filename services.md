# Services in Kubernetes

## What is a Service?

A Service is a Kubernetes object that provides a stable network endpoint for a group of Pods.

Since Pod IPs change when Pods restart, a Service ensures applications remain accessible.

---

# Why Services?

Without a Service:

- Pod IP changes after restart
- Applications become unreachable

With a Service:

- Stable IP
- Stable DNS
- Load Balancing
- Service Discovery

---

# Types of Services

## 1. ClusterIP

- Default Service type
- Accessible only inside the cluster

Use Case:
Internal communication between microservices.

---

## 2. NodePort

- Exposes application on a Node Port
- Accessible from outside the cluster

Example:

```
<NodeIP>:30080
```

---

## 3. LoadBalancer

- Creates an external Load Balancer
- Used in cloud providers (AWS, Azure, GCP)

Use Case:
Production web applications.

---

## 4. ExternalName

Maps a Service to an external DNS name.

Example:

```
database.company.com
```

---

# Create Service

```bash
kubectl apply -f service.yaml
```

---

# List Services

```bash
kubectl get svc
```

---

# Describe Service

```bash
kubectl describe svc nginx-service
```

---

# Delete Service

```bash
kubectl delete svc nginx-service
```

---

# Advantages

- Stable Networking
- Load Balancing
- Service Discovery
- High Availability

---

# Real World Example

Three Nginx Pods are running.

A ClusterIP Service forwards requests to all Pods automatically.

---

# Interview Questions

### Why do we need Services?

To provide a stable network endpoint for Pods.

### Which Service type is default?

ClusterIP.

### Which Service exposes applications externally?

NodePort and LoadBalancer.

### Which command lists Services?

```bash
kubectl get svc
```