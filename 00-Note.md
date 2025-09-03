kubectl get pods -o custom-columns="NAME:.metadata.name,PRIORITY:.spec.priorityClassName"
NAME            PRIORITY
high-prio-pod   high-priority
low-prio-pod    low-priority

# kubectl get events -o wide
this command list all the event in the namespace.
