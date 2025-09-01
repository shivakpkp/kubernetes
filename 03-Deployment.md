# Deployment
In Kubernetes, a Deployment is a controller that manages Pods and ReplicaSets. It ensures the desired number of Pod replicas are running, supports rolling updates, and makes it easy to scale or roll back applications.

# Deployment Manifest

```bash
apiVersion: app/v1
kind: Deployment
metadata:
  namespace: <NS-Name> #Optional
  name: <Deployment-name>
  labales:
    key: value
spec:
  replicas: <Number of Replicas>
  selector:
    matchlabales:
      key: value
  spec:
    containers:
      - name: <Container Name>
        image: <Image Name>
        ports:
          - containerPort: <Port>