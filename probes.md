# Probes in Kubernetes

## What are Probes?

Probes are health checks used by Kubernetes to determine the status of a container.

They help Kubernetes decide whether a container is healthy, ready to receive traffic, or still starting.

---

# Types of Probes

Kubernetes supports three types of probes:

- Liveness Probe
- Readiness Probe
- Startup Probe

---

# Liveness Probe

Checks whether a container is running correctly.

If the probe fails repeatedly, Kubernetes restarts the container.

Example Use Case:

- Application is stuck
- Deadlock
- Infinite loop

---

# Readiness Probe

Checks whether a container is ready to serve traffic.

If the probe fails, Kubernetes removes the Pod from the Service endpoints.

Example:

Application is still loading data.

---

# Startup Probe

Checks whether the application has started successfully.

Useful for slow-starting applications.

It prevents Kubernetes from killing the container during startup.

---

# Probe Types

Kubernetes supports:

- HTTP GET
- TCP Socket
- Exec Command

---

# Example Commands

View Pod

```bash
kubectl get pods
```

Describe Pod

```bash
kubectl describe pod nginx
```

Check Events

```bash
kubectl get events
```

---

# Advantages

- Self Healing
- Zero Downtime
- Better Reliability
- Automatic Recovery

---

# Real World Example

A Spring Boot application takes 60 seconds to start.

A Startup Probe prevents unnecessary restarts.

A Readiness Probe ensures traffic starts only after initialization.

---

# Interview Questions

### What is a Liveness Probe?

Checks whether the container is alive.

---

### What is a Readiness Probe?

Checks whether the application is ready to receive traffic.

---

### What is a Startup Probe?

Checks whether the application has completed startup.

---

### Can a Pod have all three probes?

Yes.