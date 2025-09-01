# What is a Pod in Kubernetes?

A **Pod** is the smallest deployable unit in Kubernetes.  
It represents **one or more containers** that run together on the same node, sharing:

- **Network** (IP, hostname, ports)  
- **Storage volumes**  

Most Pods have a single container, but they can include multiple tightly coupled containers (e.g., main app + sidecar).  
Pods are **ephemeral**, so they are usually managed by higher-level controllers like **Deployments** or **ReplicaSets**.


# How to create a Pod

You can create a Pod using the following command:

```bash
kubectl run <Container-Name> --image=<Container Image>
```
# Manifest for creating Pod:

```bash
apiVersion: v1
kind: Pod
metadata:
  namespace: <NS-Name> #Optional
  name: <Pod-Name>
  labels:
    <Key>: <Value>
spec:
  containers:
    - name: <Container-Name>
      image: <Image-Name>
      ports:
        - containerPort: <Port>
```