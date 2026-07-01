# Secrets in Kubernetes

## What is a Secret?

A Secret is a Kubernetes object used to store sensitive information securely.

Examples:

- Passwords
- API Keys
- Database Credentials
- SSH Keys
- TLS Certificates

---

# Why Secrets?

Sensitive data should never be stored directly inside application code or ConfigMaps.

Secrets provide a secure way to manage confidential information.

---

# Benefits

- Secure Storage
- Easy Management
- Decouples Secrets from Code
- Supports Environment Variables and Volumes

---

# Create Secret

```bash
kubectl apply -f secret.yaml
```

---

# List Secrets

```bash
kubectl get secrets
```

---

# Describe Secret

```bash
kubectl describe secret app-secret
```

---

# Delete Secret

```bash
kubectl delete secret app-secret
```

---

# View Secret

```bash
kubectl get secret app-secret -o yaml
```

---

# Decode Secret

```bash
echo cGFzc3dvcmQ= | base64 --decode
```

---

# Use Secret in a Pod

```yaml
envFrom:
- secretRef:
    name: app-secret
```

---

# Advantages

- Secure Credential Management
- Centralized Storage
- Easy Rotation
- Better Security

---

# ConfigMap vs Secret

| ConfigMap | Secret |
|-----------|--------|
| Non-sensitive data | Sensitive data |
| Plain text | Base64 encoded |
| App configuration | Passwords, API Keys |

---

# Real World Example

Store:

- Database Username
- Database Password
- AWS Access Keys
- JWT Secret

inside a Kubernetes Secret instead of hardcoding them.

---

# Interview Questions

### What is a Secret?

A Secret stores sensitive information securely.

### Is Secret encrypted?

By default, values are Base64 encoded. For stronger security, enable Encryption at Rest.

### Can Secrets be mounted as files?

Yes.

### Which command lists Secrets?

```bash
kubectl get secrets
```