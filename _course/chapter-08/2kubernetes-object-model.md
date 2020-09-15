---
title: "Kubernetes Object Model"
permalink: /course/chapter-8/kubernetes-object-model
---
Kubernetes has a very rich object model, representing different persistent entities in the Kubernetes cluster. Those entities describe:

-   What containerized applications we are running and on which node
-   Application resource consumption
-   Different policies attached to applications, like restart/upgrade policies, fault tolerance, etc.

With each object, we declare our intent `spec` section. The Kubernetes system manages the `status` section for objects, where it records the actual state of the object. At any given point in time, the Kubernetes Control Plane tries to match the object's actual state to the object's desired state.

Examples of Kubernetes objects are Pods, ReplicaSets, Deployments, Namespaces, etc. We will explore them next.

When creating an object, the object's configuration data section from below the `spec` field has to be submitted to the Kubernetes API server. The `spec` section describes the desired state, along with some basic information, such as the object's name. The API request to create an object must have the `spec` section, as well as other details. Although the API server accepts object definition files in a JSON format, most often we provide such files in a YAML format which is converted by `kubectl` in a JSON payload and sent to the API server.

Below is an example of a [Deployment](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) object's configuration in YAML format:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  labels:
    app: nginx
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.15.11
        ports:
        - containerPort: 80
```

The `apiVersion `field is the first required field, and it specifies the API endpoint on the API server which we want to connect to; it must match an existing version for the object type defined. The second required field is `kind`, specifying the object type - in our case it is `Deployment`, but it can be Pod, Replicaset, Namespace, Service, etc. The third required field `metadata`, holds the object's basic information, such as name, labels, namespace, etc. Our example shows two `spec `fields (`spec` and `spec.template.spec`). The fourth required field `spec` marks the beginning of the block defining the desired state of the Deployment object. In our example, we want to make sure that 3 Pods are running at any given time. The Pods are created using the Pods Template defined in `spec.template`. A nested object, such as the Pod being part of a Deployment, retains its `metadata` and `spec` and loses the `apiVersion` and `kind` - both being replaced by `template`. In `spec.template.spec`, we define the desired state of the Pod. Our Pod creates a single container running the `nginx:1.15.11` image from [Docker Hub](https://hub.docker.com/_/nginx).

Once the Deployment object is created, the Kubernetes system attaches the `status` field to the object; we will explore it later.

Next, we will take a closer look at some of the Kubernetes objects, along with other building blocks.