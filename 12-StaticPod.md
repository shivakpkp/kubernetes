# Static Pod
When you don't have kubernetes cluster and Management services. Pods can be run on worker node by Kubelet.
the pod definitions should copy to the directory ***/etc/kubernetes/manifests***
Kubelete, will create the pod according to definition and monitor them to be up and running.

# UseCases
the controlplan pod can be ceate in this case. So you do not need to download the binary and install it.
the kubelet takes care of the Pods

# Kubelet Service

It can be refer to the pass
```bash
ExecuteStart=/usr/local/bin/kubelet \\
    --container-runtime=remote \\
    --container-runtime-endpoint=unix:///var/run/containerd/containerd.sock //
    --pod-manifest-path=/etc/kubernetes/manifest \\    #The pass should be Set Here
    --kubeconfig=/var/lib/kubelet/kubeconfig \\
    --network-plugin=cni \\
    --register-node=true \\
    --v=2
```
**OR**
It can refer to the file which has the pass

```bash
ExecuteStart=/usr/local/bin/kubelet \\
    --container-runtime=remote \\
    --container-runtime-endpoint=unix:///var/run/containerd/containerd.sock //
    --config=kubeconfig.yml \\    #The filename should set here
    --kubeconfig=/var/lib/kubelet/kubeconfig \\
    --network-plugin=cni \\
    --register-node=true \\
    --v=2
```
***kubeconfig.yaml***
```bash
staticPodPath: /etc/kubernetes/manifest
```