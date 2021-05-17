# Difference between Pod and Deployment?

```
Pod is a collection of containers and basic object of Kuberntes. All containers of pod lie in same node.

Not suitable for production
No rolling updates
Deployment is a kind of controller in Kubernetes.

Controllers use a Pod Template that you provide to create the Pods for which it is responsible.

Deployment creates a ReplicaSet which in turn make sure that, CurrentReplicas is always same as desiredReplicas .

Advantages :

You can rollout and rollback your changes using deployment
Monitors the state of each pod
Best suitable for production
Supports rolling updates
```
