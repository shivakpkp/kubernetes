# DeamonSet

DeamonSet is similar to replicaSet but it creates pod on each node. The usecases are Monitoring Tools or Log collector

# DeamonSet Command

```bash
kubectl apply -f deamonset-definition.yml
kubectl get deamonset
kubectl describe deamonset <DeamonSet name>
```

# DeamonSet Manifest
```bash
apiVersion: app/v1
kind: deamonSet
metadata:
  name: <Name of deamon>
  labels:
    key:value
spec:
  selector:
    matchLabels:
      key: value
  template:
    metadata:
      name: <Pod Name>
      labales:
        key: value
    spec:
      containers:
        - name: <Container name>
          image: <image Name>
```
