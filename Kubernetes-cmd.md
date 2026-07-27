# Kubernetes (kubectl) Command Cheat Sheet

> A complete guide to Kubernetes (`kubectl`) commands for developers and DevOps engineers.

---

# Table of Contents

1. Installation
2. Cluster Information
3. Contexts & Namespaces
4. Pods
5. Deployments
6. Services
7. ReplicaSets
8. ConfigMaps
9. Secrets
10. Persistent Volumes
11. Jobs & CronJobs
12. Ingress
13. Scaling
14. Rolling Updates
15. Logs & Debugging
16. Resource Management
17. Port Forwarding
18. Copy Files
19. Execute Commands
20. YAML Management
21. Monitoring
22. Troubleshooting
23. Developer Workflow
24. Essential Commands
25. Best Practices

---

# 1. Installation

Check Version

```bash
kubectl version --client
```

Cluster Version

```bash
kubectl version
```

---

# 2. Cluster Information

Cluster Info

```bash
kubectl cluster-info
```

Cluster Nodes

```bash
kubectl get nodes
```

Describe Node

```bash
kubectl describe node node-name
```

---

# 3. Contexts & Namespaces

Current Context

```bash
kubectl config current-context
```

List Contexts

```bash
kubectl config get-contexts
```

Switch Context

```bash
kubectl config use-context production
```

List Namespaces

```bash
kubectl get namespaces
```

Create Namespace

```bash
kubectl create namespace dev
```

Delete Namespace

```bash
kubectl delete namespace dev
```

---

# 4. Pods

List Pods

```bash
kubectl get pods
```

All Namespaces

```bash
kubectl get pods -A
```

Wide Output

```bash
kubectl get pods -o wide
```

Describe Pod

```bash
kubectl describe pod pod-name
```

Delete Pod

```bash
kubectl delete pod pod-name
```

---

# 5. Deployments

List

```bash
kubectl get deployments
```

Create

```bash
kubectl create deployment nginx --image=nginx
```

Describe

```bash
kubectl describe deployment nginx
```

Delete

```bash
kubectl delete deployment nginx
```

---

# 6. Services

List

```bash
kubectl get svc
```

Expose Deployment

```bash
kubectl expose deployment nginx \
--port=80 \
--type=LoadBalancer
```

Describe

```bash
kubectl describe svc nginx
```

---

# 7. ReplicaSets

List

```bash
kubectl get replicasets
```

Describe

```bash
kubectl describe rs
```

---

# 8. ConfigMaps

Create

```bash
kubectl create configmap app-config \
--from-file=config.env
```

List

```bash
kubectl get configmaps
```

Describe

```bash
kubectl describe configmap app-config
```

---

# 9. Secrets

Create Secret

```bash
kubectl create secret generic app-secret \
--from-literal=password=secret
```

List

```bash
kubectl get secrets
```

Describe

```bash
kubectl describe secret app-secret
```

---

# 10. Persistent Volumes

List PVs

```bash
kubectl get pv
```

List PVCs

```bash
kubectl get pvc
```

Describe

```bash
kubectl describe pvc data
```

---

# 11. Jobs & CronJobs

Jobs

```bash
kubectl get jobs
```

CronJobs

```bash
kubectl get cronjobs
```

---

# 12. Ingress

List

```bash
kubectl get ingress
```

Describe

```bash
kubectl describe ingress app
```

---

# 13. Scaling

Scale Deployment

```bash
kubectl scale deployment api \
--replicas=5
```

Autoscaler

```bash
kubectl autoscale deployment api \
--cpu-percent=70 \
--min=2 \
--max=10
```

---

# 14. Rolling Updates

Update Image

```bash
kubectl set image deployment/api \
api=myimage:v2
```

Status

```bash
kubectl rollout status deployment/api
```

History

```bash
kubectl rollout history deployment/api
```

Undo Rollout

```bash
kubectl rollout undo deployment/api
```

---

# 15. Logs & Debugging

Logs

```bash
kubectl logs pod-name
```

Follow Logs

```bash
kubectl logs -f pod-name
```

Previous Logs

```bash
kubectl logs -p pod-name
```

---

# 16. Resource Management

Top Pods

```bash
kubectl top pods
```

Top Nodes

```bash
kubectl top nodes
```

---

# 17. Port Forwarding

Forward Port

```bash
kubectl port-forward pod-name 8080:80
```

---

# 18. Copy Files

Copy to Pod

```bash
kubectl cp app.txt pod-name:/tmp
```

Copy from Pod

```bash
kubectl cp pod-name:/tmp/log.txt .
```

---

# 19. Execute Commands

Shell

```bash
kubectl exec -it pod-name -- sh
```

Bash

```bash
kubectl exec -it pod-name -- bash
```

---

# 20. YAML Management

Apply

```bash
kubectl apply -f deployment.yaml
```

Delete

```bash
kubectl delete -f deployment.yaml
```

Dry Run

```bash
kubectl apply -f app.yaml --dry-run=client
```

---

# 21. Monitoring

Events

```bash
kubectl get events
```

Sorted Events

```bash
kubectl get events \
--sort-by=.metadata.creationTimestamp
```

---

# 22. Common Problems

Pod Not Starting

```bash
kubectl describe pod pod-name
```

CrashLoopBackOff

```bash
kubectl logs pod-name
```

Image Pull Error

```bash
kubectl describe pod pod-name
```

---

# 23. Developer Workflow

```bash
kubectl apply -f deployment.yaml

kubectl get pods

kubectl logs -f api-pod

kubectl rollout status deployment/api

kubectl get svc

kubectl get ingress
```

---

# 24. Essential Commands

```bash
kubectl get
kubectl describe
kubectl create
kubectl apply
kubectl delete
kubectl edit
kubectl logs
kubectl exec
kubectl cp
kubectl port-forward
kubectl scale
kubectl rollout
kubectl top
kubectl config
kubectl cluster-info
```

---

# 25. Best Practices

- Use declarative YAML with `kubectl apply`.
- Store manifests in version control.
- Organize resources using namespaces.
- Set CPU and memory requests/limits.
- Use ConfigMaps and Secrets instead of hardcoding configuration.
- Use readiness and liveness probes.
- Monitor deployments after every rollout.
- Prefer rolling updates over deleting and recreating deployments.
- Avoid using the `default` namespace for production workloads.