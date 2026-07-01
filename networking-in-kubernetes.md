# Networking in Kubernetes

## Introduction

Kubernetes networking enables communication between Pods, Services, and external clients.

Every Pod receives its own unique IP address, allowing direct communication without Network Address Translation (NAT).

---

# Kubernetes Networking Goals

- Every Pod gets a unique IP
- Pods can communicate with each other
- Services provide stable networking
- External users can access applications
- DNS-based service discovery

---

# Pod-to-Pod Communication

Pods communicate directly using their IP addresses.

Example:

```
Pod A  --->  Pod B
10.244.1.5    10.244.2.8
```

No NAT is required.

---

# Pod-to-Service Communication

Instead of accessing Pod IPs directly, applications use a Service.

```
Client
   │
   ▼
Service (ClusterIP)
   │
   ▼
Pods
```

The Service forwards requests to healthy Pods.

---

# Service Types

## ClusterIP

- Default
- Internal communication only

---

## NodePort

- Exposes Service on a Node port

Example:

```
<NodeIP>:30080
```

---

## LoadBalancer

Creates an external load balancer.

Commonly used in:

- AWS
- Azure
- Google Cloud

---

## ExternalName

Maps a Service to an external DNS name.

---

# Kubernetes DNS

Every Service automatically receives a DNS name.

Example:

```
mysql.default.svc.cluster.local
```

Applications communicate using DNS instead of IP addresses.

---

# Container Network Interface (CNI)

CNI plugins provide networking for Pods.

Popular CNI Plugins:

- Calico
- Flannel
- Cilium
- Weave Net

---

# kube-proxy

kube-proxy manages networking rules for Services.

Responsibilities:

- Load Balancing
- Traffic Routing
- Service Discovery

---

# Network Policies

Network Policies control traffic between Pods.

They improve security by allowing or denying network access.

Example:

- Allow frontend → backend
- Block unknown Pods

---

# Networking Flow

```
Internet
      │
      ▼
Ingress
      │
      ▼
Service
      │
      ▼
Pods
```

---

# Advantages

- Flat Networking
- Service Discovery
- Internal Load Balancing
- Secure Communication
- Scalability

---

# Interview Questions

### Does every Pod have its own IP?

Yes.

---

### Which component provides Service networking?

kube-proxy.

---

### What is CNI?

Container Network Interface used for Pod networking.

---

### Name popular CNI plugins.

- Calico
- Flannel
- Cilium
- Weave Net

---

### Which Service type is used internally?

ClusterIP.