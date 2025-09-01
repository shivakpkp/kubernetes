# Default CPU Limit Range Definition
```bash
apiVersion: v1
kind: LimitRange
metadata: 
  name: CPU-Resource-Constarint

spec:
  limits:
  - default:
      cpu: 500m
    defaultRequest:
      cpu: 500m
    max:
      cpu: 1
    min:
      cpu: 100m
    type:
      container
```
# Default Memory Limit Range Definition
```bash
apiVersion: v1
kind: LimitRange
metadata: 
  name: CPU-Resource-Constarint

spec:
  limits:
  - default:
      memory: 1Gi
    defaultRequest:
      memory: 1Gi
    max:
      memory: 1Gi
    min:
      memory: 500Mi
    type:
      container
```

# Hard Limit for CPU and Memory Limit in specific Namespace 

```bash
apiVersion: v1
kind: ResourceQuota
metadata: 
  name: my-Resource-quota

spec:
  hard:
    resquests.cpu: 4
    requests.memory: 4Gi
    limits.cpu: 10
    limits.memory: 10Gi
```