# Jobs and CronJobs in Kubernetes

## What is a Job?

A Job creates one or more Pods and ensures they successfully complete a task.

Unlike a Deployment, a Job finishes after completing its work.

Examples:

- Database Backup
- Data Migration
- Report Generation
- Batch Processing

---

# What is a CronJob?

A CronJob creates Jobs on a schedule.

It works like Linux cron.

Examples:

- Daily Backup
- Weekly Reports
- Log Cleanup
- Database Maintenance

---

# Job vs CronJob

| Job | CronJob |
|------|----------|
| Runs once | Runs on a schedule |
| Manual execution | Automatic execution |
| Used for one-time tasks | Used for recurring tasks |

---

# Create Job

```bash
kubectl apply -f job.yaml
```

---

# Create CronJob

```bash
kubectl apply -f cronjob.yaml
```

---

# List Jobs

```bash
kubectl get jobs
```

---

# List CronJobs

```bash
kubectl get cronjobs
```

---

# Delete Job

```bash
kubectl delete job backup-job
```

---

# Delete CronJob

```bash
kubectl delete cronjob backup-cronjob
```

---

# Advantages

- Automated Tasks
- Scheduled Execution
- Reliable Batch Processing
- Easy Maintenance

---

# Real World Example

A company runs:

- Database backup every night
- Cleanup old logs every Sunday
- Generate monthly reports

using CronJobs.

---

# Interview Questions

### What is a Job?

A Job runs a task until it completes successfully.

---

### What is a CronJob?

A CronJob runs Jobs on a schedule.

---

### Which format is used for scheduling?

Cron expression.

Example:

```text
0 2 * * *
```

Runs every day at 2:00 AM.

---

### Difference between Job and Deployment?

Deployment runs continuously.

Job finishes after completing its task.