# Node Selector
A pod can land on a node by label the node and add node selector to pod.

# How to label the node

```bash
kubectl label nodes <NODE-NAME> <Label-Key>=<Label-Value>
```

# How to add node Selector to Pod

```bash
apiVersion: v1
kind: Pod
metadata:
  name: POD-NAME
  labels:
    Key: Value
spec:
  containers:
    - name: <Container-Name>
      image: <Container-Image>
  nodeSelecor:
    <Label-Key>: <Label-Value>
```