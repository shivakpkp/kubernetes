# Services
In Kubernetes, a Service is an abstraction that defines a stable way to access a set of Pods. Since Pods are temporary and their IPs change, Services provide a fixed IP address and DNS name to reliably expose applications inside or outside the cluster.

# ClusterIP

 In Kubernetes, a ClusterIP is the default Service type. It exposes a Service on an internal IP that’s only accessible within the cluster. It’s mainly used for communication between Pods and microservices, not for external access.

 ```bash
apiVersion:
kind: Service
metadata:
  name: <Service-Name>
spec:
  type: ClusterIp
  selector:
    key: value
  ports:
   - Targetport: <container-port>
     port: <Service-port>
     protocol: TCP
 ```
# NodePort

In Kubernetes, a NodePort Service exposes an application on a static port (30000–32767) of each worker node’s IP. This allows external traffic to access the app using <NodeIP>:<NodePort>. It’s the simplest way to make a Service available outside the cluster.

```bash
apiVersion:
kind: Service
metadata:
  name: <Service-name>
spec:
  type: NodePort
  selector:
    key: value
  ports:
    - targetPort: <Pod's container port> # Pod's container port
      port: <Service-port> # Service port inside cluster
      nodePort: <exposed port>  # Port exposed on each Node
```

# LoadBalancer

In Kubernetes, a LoadBalancer Service exposes an application to the internet by provisioning an external load balancer (from the cloud provider). It distributes incoming traffic across the Pods, giving users a single external IP to access the app.

```bash
apiVersion:
kind: Service
metadata:
  namespace: <NS-Name> #Optional
  name: <Service-name>
spec:
  type: LoadBalancer
  selector:
    key: value
  ports:
    - targetPort: <Pod's container port> # Pod's container port
      port: <Service-port> # Service port inside cluster
```