# priority Class
When you create Pods in the cluster, if there is not available spce for creating pod, your pod won't be created.
if it is high priority pod then it is possible to create priority class and pod with less priority class will be remove and pods with higher priority class will be created.
 for apps it's range is **1,000,000,000 TO (-2,147,483,648)**
 for kubernetes Component it's range is ** 1,000,000,000 To 2,000,000,000 **

# get priority command
```bash
kubectl get priorityclass
```
# priority defenition

```bash
apiVersion: scheduling.k8s.io/v1
kind: PriorityClass
metadata: 
  name: high-priority  # Priority Name
value: 1000000000
description "For critical pods"
preemptionPolicy: PreemptLowerPriority # Kill the lower P jobs   
#preemptionPlicy: never # do not kill the lower P jobs
```

# Pod Definition:

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
  priorityClassName: high-priority  # Priority Name
```


