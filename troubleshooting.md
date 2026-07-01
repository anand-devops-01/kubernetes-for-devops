# Kubernetes Troubleshooting Guide

## Introduction

Troubleshooting is the process of identifying and fixing issues in a Kubernetes cluster.

Common issues include:

- Pods not starting
- CrashLoopBackOff
- ImagePullBackOff
- Pending Pods
- Service connectivity issues

---

# Check Cluster

```bash
kubectl cluster-info
```

---

# Check Nodes

```bash
kubectl get nodes
```

---

# Check Pods

```bash
kubectl get pods
```

---

# Describe Pod

```bash
kubectl describe pod <pod-name>
```

Shows:

- Events
- Errors
- Scheduling Issues
- Image Errors

---

# View Logs

```bash
kubectl logs <pod-name>
```

For multi-container Pods:

```bash
kubectl logs <pod-name> -c <container-name>
```

---

# Execute Inside a Pod

```bash
kubectl exec -it <pod-name> -- /bin/bash
```

---

# Common Errors

## CrashLoopBackOff

Cause:

- Application crash
- Wrong configuration
- Missing dependencies

Solution:

- Check logs
- Verify configuration
- Fix application errors

---

## ImagePullBackOff

Cause:

- Wrong image name
- Private registry
- Network issues

Solution:

- Verify image
- Check registry credentials
- Confirm internet connectivity

---

## Pending Pod

Cause:

- Insufficient CPU or Memory
- No matching node
- PVC not available

Solution:

- Check node resources
- Verify scheduler events
- Inspect PVC status

---

## Service Not Working

Cause:

- Wrong selector
- Incorrect port
- Pod labels mismatch

Solution:

- Verify Service selector
- Check Pod labels
- Confirm targetPort

---

# Useful Commands

```bash
kubectl get all
```

```bash
kubectl get events
```

```bash
kubectl describe node <node-name>
```

```bash
kubectl top nodes
```

```bash
kubectl top pods
```

---

# Troubleshooting Workflow

1. Check Pod Status
2. Describe the Pod
3. View Logs
4. Check Events
5. Verify Service
6. Verify Deployment
7. Verify Node Resources

---

# Interview Questions

### How do you troubleshoot a Pod that is not running?

- Check Pod status
- Describe the Pod
- Review logs
- Inspect events

---

### Which command shows Pod logs?

```bash
kubectl logs <pod-name>
```

---

### Which command shows Pod events?

```bash
kubectl describe pod <pod-name>
```

---

### What causes ImagePullBackOff?

Usually an incorrect image name, registry issue, or authentication failure.

---

### What causes CrashLoopBackOff?

Application crashes repeatedly after starting.