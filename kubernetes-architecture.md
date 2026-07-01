# Kubernetes Architecture ☸️

## Overview

Kubernetes follows a Master-Worker architecture.

A Kubernetes cluster consists of:

- Control Plane (Master Node)
- Worker Nodes

```
              +----------------------+
              |    Control Plane     |
              |----------------------|
              | API Server           |
              | Scheduler            |
              | Controller Manager   |
              | ETCD                 |
              +----------+-----------+
                         |
        --------------------------------------
        |                                    |
+-------------------+             +-------------------+
|   Worker Node 1   |             |   Worker Node 2   |
|-------------------|             |-------------------|
| Kubelet           |             | Kubelet           |
| Kube Proxy        |             | Kube Proxy        |
| Container Runtime |             | Container Runtime |
| Pods              |             | Pods              |
+-------------------+             +-------------------+
```

---

# Control Plane Components

## API Server

- Entry point of Kubernetes
- Accepts kubectl requests
- Communicates with all components
- Stores cluster state in ETCD

---

## ETCD

- Distributed Key-Value Database
- Stores cluster information
- Stores configuration
- Stores Secrets and ConfigMaps

---

## Scheduler

Responsible for deciding

**Which Worker Node should run a Pod?**

Scheduler checks:

- CPU
- Memory
- Node Availability
- Constraints

---

## Controller Manager

Continuously checks cluster state.

Examples

- Deployment Controller
- ReplicaSet Controller
- Node Controller
- Job Controller

---

# Worker Node Components

## Kubelet

Agent running on every worker node.

Responsibilities:

- Talks to API Server
- Starts Pods
- Monitors Pods
- Reports Node Status

---

## Kube Proxy

Responsible for networking.

Functions:

- Service Networking
- Load Balancing
- Traffic Forwarding

---

## Container Runtime

Runs containers.

Examples:

- containerd
- CRI-O

Earlier Docker was commonly used as the runtime.

---

# Architecture Flow

1. User runs kubectl command.
2. API Server receives the request.
3. Scheduler selects a Worker Node.
4. Controller Manager creates required objects.
5. Kubelet starts Pods.
6. Kube Proxy exposes networking.
7. ETCD stores cluster state.

---

# Interview Questions

## What is the Control Plane?

The Control Plane manages the Kubernetes cluster.

---

## What is ETCD?

A distributed key-value database that stores cluster state.

---

## What is Kubelet?

An agent running on every Worker Node.

---

## What is Kube Proxy?

A networking component responsible for service communication.

---

## Which component schedules Pods?

Kubernetes Scheduler.