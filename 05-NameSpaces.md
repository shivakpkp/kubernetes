# NameSpaces

In Kubernetes, a Namespace is a virtual cluster within a Kubernetes cluster. It helps organize and isolate resources (like Pods, Services, and Deployments) for different teams, projects, or environments without needing separate clusters.

# NameSpace Manifest

```bash
apiVersion: v1
kind: NameSpaces
metadata:
  name: <NS-Name>
  