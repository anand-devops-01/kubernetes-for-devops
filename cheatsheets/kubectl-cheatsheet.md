# Kubectl Cheat Sheet

## Cluster Information

```bash
kubectl cluster-info
kubectl version
kubectl config view
kubectl config current-context
kubectl config get-contexts
```

---

# Nodes

```bash
kubectl get nodes
kubectl describe node <node-name>
kubectl top nodes
```

---

# Pods

```bash
kubectl get pods
kubectl get pods -A
kubectl get pods -o wide
kubectl describe pod <pod-name>
kubectl logs <pod-name>
kubectl exec -it <pod-name> -- /bin/bash
kubectl delete pod <pod-name>
```

---

# Deployments

```bash
kubectl get deployments
kubectl describe deployment <deployment-name>
kubectl scale deployment <deployment-name> --replicas=3
kubectl rollout status deployment <deployment-name>
kubectl rollout history deployment <deployment-name>
kubectl rollout undo deployment <deployment-name>
```

---

# ReplicaSets

```bash
kubectl get rs
kubectl describe rs <replicaset-name>
```

---

# Services

```bash
kubectl get svc
kubectl describe svc <service-name>
```

---

# Namespaces

```bash
kubectl get namespaces
kubectl create namespace dev
kubectl delete namespace dev
```

---

# ConfigMaps

```bash
kubectl get configmaps
kubectl describe configmap <configmap-name>
```

---

# Secrets

```bash
kubectl get secrets
kubectl describe secret <secret-name>
```

---

# Volumes

```bash
kubectl get pv
kubectl get pvc
kubectl describe pvc <pvc-name>
```

---

# Jobs & CronJobs

```bash
kubectl get jobs
kubectl get cronjobs
```

---

# RBAC

```bash
kubectl get roles
kubectl get rolebindings
kubectl get clusterroles
kubectl get clusterrolebindings
```

---

# Events

```bash
kubectl get events
kubectl describe pod <pod-name>
```

---

# Resource Usage

```bash
kubectl top pods
kubectl top nodes
```

---

# Apply & Delete Resources

```bash
kubectl apply -f file.yaml
kubectl delete -f file.yaml
```

---

# Debugging

```bash
kubectl logs <pod-name>
kubectl describe pod <pod-name>
kubectl exec -it <pod-name> -- /bin/bash
kubectl get events
```

---

# Useful Shortcuts

| Command | Meaning |
|---------|---------|
| kubectl get po | Pods |
| kubectl get deploy | Deployments |
| kubectl get svc | Services |
| kubectl get ns | Namespaces |
| kubectl get rs | ReplicaSets |
| kubectl get cm | ConfigMaps |
| kubectl get pvc | PersistentVolumeClaims |
| kubectl get pv | PersistentVolumes |
| kubectl get ing | Ingress |

---

# Quick Revision

- `kubectl get pods` → List Pods
- `kubectl logs` → View Logs
- `kubectl exec` → Access Container
- `kubectl describe` → Detailed Resource Info
- `kubectl apply -f` → Create/Update Resources
- `kubectl delete -f` → Delete Resources
- `kubectl top pods` → Resource Usage
- `kubectl rollout undo` → Rollback Deployment