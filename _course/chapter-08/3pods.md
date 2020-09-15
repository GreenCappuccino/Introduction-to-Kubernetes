---
title: "Pods"
permalink: /course/chapter-8/pods
---
A [Pod](https://kubernetes.io/docs/concepts/workloads/pods/pod-overview/) is the smallest and simplest Kubernetes object. It is the unit of deployment in Kubernetes, which represents a single instance of the application. A Pod is a logical collection of one or more containers, which:

-   Are scheduled together on the same host with the Pod
-   Share the same network namespace
-   Have access to mount the same external storage (volumes).

{% include figure image_path="/assets/images/Pods.png" alt="A pod is a collection of one or more containers" caption="Pods"%}

Pods are ephemeral in nature, and they do not have the capability to self-heal by themselves. That is the reason they are used with controllers which handle Pods' replication, fault tolerance, self-healing, etc. Examples of controllers are Deployments, ReplicaSets, ReplicationControllers, etc. We attach a nested Pod's specification to a controller object using the Pod Template, as we have seen in the previous section.

Below is an example of a Pod object's configuration in `YAML` format:

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx-pod
  labels:
    app: nginx
spec:
  containers:
  - name: nginx
    image: nginx:1.15.11
    ports:
    - containerPort: 80
```

The `apiVersion `field must specify **v1** for the **Pod** object definition. The second required field is `kind` specifying the `Pod` object type. The third required field `metadata`, holds the object's name and label. The fourth required field `spec` marks the beginning of the block defining the desired state of the Pod object - also named the `PodSpec`. Our Pod creates a single container running the `nginx:1.15.11` image from [Docker Hub](https://hub.docker.com/_/nginx).