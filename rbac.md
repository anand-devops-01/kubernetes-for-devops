# Role-Based Access Control (RBAC)

## What is RBAC?

RBAC (Role-Based Access Control) is a Kubernetes security mechanism used to control who can access and perform actions on cluster resources.

RBAC follows the principle of least privilege, meaning users only get the permissions they need.

---

# Why RBAC?

RBAC helps to:

- Secure the cluster
- Restrict user access
- Control permissions
- Support multiple teams
- Improve compliance

---

# RBAC Components

## Role

Defines permissions within a Namespace.

Example:

- Read Pods
- Create ConfigMaps
- Delete Services

---

## ClusterRole

Defines permissions across the entire cluster.

Example:

- Manage Nodes
- View all Namespaces

---

## RoleBinding

Assigns a Role to a User, Group, or ServiceAccount within a Namespace.

---

## ClusterRoleBinding

Assigns a ClusterRole across the entire cluster.

---

# RBAC Flow

```
User
   │
   ▼
RoleBinding
   │
   ▼
Role
   │
   ▼
Permissions
```

---

# Useful Commands

List Roles

```bash
kubectl get roles
```

List ClusterRoles

```bash
kubectl get clusterroles
```

List RoleBindings

```bash
kubectl get rolebindings
```

List ClusterRoleBindings

```bash
kubectl get clusterrolebindings
```

---

# Advantages

- Better Security
- Fine-Grained Access Control
- Multi-Team Support
- Least Privilege Principle

---

# Real World Example

Developers:

- View Pods
- View Logs

Administrators:

- Full cluster access

---

# Interview Questions

### What is RBAC?

RBAC controls access to Kubernetes resources.

---

### Difference between Role and ClusterRole?

Role is Namespace-scoped.

ClusterRole is Cluster-wide.

---

### What is RoleBinding?

It connects a Role with a User or ServiceAccount.

---

### What is the principle of least privilege?

Give users only the permissions they need.