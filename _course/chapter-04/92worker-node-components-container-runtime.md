---
title: "Worker Node Components: Container Runtime"
permalink: /course/chapter-4/worker-node-components-container-runtime
---
Although Kubernetes is described as a "container orchestration engine", it does not have the capability to directly handle containers. In order to run and manage a container's lifecycle, Kubernetes requires a **container runtime** on the node where a Pod and its containers are to be scheduled. Kubernetes supports many container runtimes:

-   [Docker](https://www.docker.com/) - although a container platform which uses **containerd** as a container runtime, it is the most widely used container runtime with Kubernetes
-   [CRI-O](https://cri-o.io/) - a lightweight container runtime for Kubernetes, it also supports Docker image registries
-   [containerd](https://containerd.io/) - a simple and portable container runtime providing robustness
-   [rkt](https://github.com/rkt/rkt) - a pod-native container engine, it also runs Docker images
-   [rktlet](https://github.com/kubernetes-incubator/rktlet) - a Kubernetes [Container Runtime Interface](https://github.com/kubernetes/community/blob/master/contributors/devel/sig-node/container-runtime-interface.md) (CRI) implementation using **rkt**.