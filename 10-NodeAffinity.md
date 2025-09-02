# Node Affinity
With node selector we are not able to do complex expression to choose a node.
But Node Affinity is more advance and we are able to select node base on complex criteria.
# label the node
```bash
kubectl label nodes <NODE-NAME> <Label-Key>=<Label-Value>
```

# Pod Definition
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
  affinity:
    nodeAffinity:
      requiredDuringSchedulingIgnoredDuringExecution: # Behavior of scheduler when place the pod
        nodeSelectorTerms:
        - matchExpressions:
          - key: size
            operator: In # NotIn, Exists 
            values:
            - Large
```

# Node Affinity Type:

***Availabe***
|             Type                                |  DuringScheduling   | DuringExecution |
| ----------------------------------------------- | ------------------- |-----------------|
| requiredDuringSchedulingIgnoreDuringExecution   |  Reuired            | Ignored         |
| preferredDuringSchedulingIgnoreDuringExecution  |  Preferred          | Ignored         |



***Planned***
|             Type                                |  DuringScheduling   | DuringExecution   |
| ----------------------------------------------- | ------------------- | ----------------- |
| requiredDuringSchedulingRequiredDuringExecution | Reuired             | Reuired           |
| preferredDuringSchedulingRequiredDuringExecution| Preffered           | Reuired           |