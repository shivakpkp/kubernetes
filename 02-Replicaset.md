# Relplicaset
In Kubernetes, replicas define how many copies of a Pod should run at the same time. They ensure high availability and load balancing. If one Pod fails, Kubernetes automatically creates another to maintain the desired number.

# Manifest File For Replicas

```bash
apiVersion: app/v1
kind: Replicaset
metadata: 
  namespace: <NS-Name> #Optional
  name: <Replicaset-Name>
  labels:
    key: value
spec:
  replicas: <Number of replicas>
  selector:
    matchLabels:
      key: value
  template:
    metadata:
      name: <Pod-Name>
      labels:
        key: value
    spec:
      containers:
      - name: <Container-Name>
        image: <image>
        ports:
         - containerPort: <port>
```
