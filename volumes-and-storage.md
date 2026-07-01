# Volumes and Storage in Kubernetes

## What is a Volume?

A Volume provides persistent or shared storage for containers running inside a Pod.

Unlike container storage, Kubernetes Volumes can survive container restarts.

---

# Why Volumes?

Without Volumes:

- Data is lost when a container restarts.
- Logs and uploaded files disappear.

Volumes provide persistent storage for applications.

---

# Types of Volumes

## 1. emptyDir

- Created when Pod starts.
- Deleted when Pod is removed.
- Used for temporary storage.

---

## 2. hostPath

- Mounts a directory from the Node.
- Mainly used for testing and development.

---

## 3. PersistentVolume (PV)

A cluster-wide storage resource created by an administrator.

Examples:

- AWS EBS
- Azure Disk
- Google Persistent Disk
- NFS

---

## 4. PersistentVolumeClaim (PVC)

A request for storage made by a Pod.

PVC connects Pods to available PersistentVolumes.

---

## 5. StorageClass

Automates creation of PersistentVolumes.

Mostly used in cloud environments.

---

# Create Persistent Volume

```bash
kubectl apply -f pv.yaml
```

---

# Create Persistent Volume Claim

```bash
kubectl apply -f pvc.yaml
```

---

# List Persistent Volumes

```bash
kubectl get pv
```

---

# List PVCs

```bash
kubectl get pvc
```

---

# Advantages

- Persistent Data
- Shared Storage
- Dynamic Provisioning
- Better Application Reliability

---

# Real World Example

A MySQL database stores its data inside a PersistentVolume.

Even if the Pod is deleted, the database files remain available.

---

# Interview Questions

### What is a PersistentVolume?

A PersistentVolume (PV) is storage available to the Kubernetes cluster.

---

### What is a PersistentVolumeClaim?

A PersistentVolumeClaim (PVC) is a request for storage made by a Pod.

---

### What is StorageClass?

StorageClass enables dynamic storage provisioning.

---

### Does emptyDir persist after Pod deletion?

No.