Taint and Toleration put restrict on the pod and node to specify which pod can schedule on the node. but it is not garanty that node with toleration run on tainted node.

```bash
kubectl taint nodes <node-name> key=value:taint-effect

3 taint-effect:
1. NoSchedule: No Pod will be schedule on the Node unless the pod with toleration
2. PreferNoSchedule: prefer not to add pod unless there is no other pod
3. NoExecute:  If there is any pod on the node before we add taint, the pod will be evacuated.
```

# Add taint to the Pod

```bash
apiVersion: v1
kind: Pod
metadata:
  name: <Pod-Name>
spec:
  container:
    - name: <Container-name>
      image: <Image-Name>
  tolerations:
    - key: "app"
      operator: "Equal"
      value: "Value"
      effect: "NoSchedule"