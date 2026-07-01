# ConfigMaps in Kubernetes

## What is a ConfigMap?

A ConfigMap is used to store non-sensitive configuration data as key-value pairs.

It helps separate application configuration from application code.

---

# Why ConfigMaps?

Instead of hardcoding configuration inside an application, Kubernetes stores it in a ConfigMap.

Examples:

- Application Name
- Environment Variables
- Port Numbers
- Database Host
- API URLs

---

# Benefits

- Decouples configuration from code
- Easy to update
- Reusable across Pods
- Better application management

---

# Create ConfigMap

```bash
kubectl apply -f configmap.yaml
```

---

# List ConfigMaps

```bash
kubectl get configmaps
```

---

# Describe ConfigMap

```bash
kubectl describe configmap app-config
```

---

# Delete ConfigMap

```bash
kubectl delete configmap app-config
```

---

# Use ConfigMap in a Pod

```yaml
envFrom:
- configMapRef:
    name: app-config
```

---

# Real World Example

Instead of writing:

```
DB_HOST=database.example.com
```

inside your application, store it in a ConfigMap and inject it into the Pod.

---

# Advantages

- Centralized Configuration
- Easy Updates
- Reusable
- Environment Specific Configurations

---

# Interview Questions

### What is a ConfigMap?

A ConfigMap stores non-sensitive configuration data.

### Can ConfigMaps store passwords?

No.

### Which command lists ConfigMaps?

```bash
kubectl get configmaps
```

### How are ConfigMaps used?

Using environment variables or mounted volumes.