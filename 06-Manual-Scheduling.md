# Manual Scheduling
If there is not scheduler in the kubernetes cluster when you run a pod it stays in the **pending**, since they is not scheduler to place the pod in the Nodes. thus you have to add the node name to the manifest.

# Pod Manifest

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
  nodename: <Node's Name>
```

# if pod has already create, it should be bind to the node

# bind Manifest

```bash
apiVersion: v1
kind: binding
metadata:
  name: <binding-name>
target:
  apiVersion: v1
  kind: Node
  name: <node's name>
```