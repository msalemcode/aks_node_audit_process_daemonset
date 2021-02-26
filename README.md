# K8s Node Audit Process Daemonset

DaemonSets in Kubernetes allow you to run a pod on every node; this is a good fit if you want to bootstrap new nodes and install software. You can configure the privileges that a DaemonSet runs with and tune the level of access you need your DaemonSet to have based on the tasks it needs to perform. This is small demo on how to run script against nodes using daemonset. 

# How to run the demo
Install the configmap first 

```
kubectl apply -f node-audit-configmap.yaml
```
Then install daemonset
```
kubectl apply -f node-audit-daemonset.yaml
```

Now using get the running pods and make sure a daemon running on each node
```
kubectl get pods -o wide
```
finally access the daemon logs

```
kubectl logs -f node-audit-xxxx
```


