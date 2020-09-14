---
title: "Worker Node Components: kubelet"
permalink: /course/chapter-4/worker-node-components-kubelet
---
The **kubelet** is an agent running on each node and communicates with the control plane components from the master node. It receives Pod definitions, primarily from the API server, and interacts with the container runtime on the node to run containers associated with the Pod. It also monitors the health of the Pod's running containers.

The kubelet connects to the container runtime using [Container Runtime Interface](https://github.com/kubernetes/community/blob/master/contributors/devel/sig-node/container-runtime-interface.md) (CRI). CRI consists of protocol buffers, gRPC API, and libraries.

{% include figure image_path="/assets/images/CRI.png" alt="Container Runtime Interface" caption="Container Runtime Interface (Retrieved from [blog.kubernetes.io](http://blog.kubernetes.io/2016/12/container-runtime-interface-cri-in-kubernetes.html))"%}

As shown above, the kubelet acting as grpc client connects to the CRI shim acting as grpc server to perform container and image operations. CRI implements two services: **ImageService** and **RuntimeService**. The **ImageService** is responsible for all the image-related operations, while the **RuntimeService** is responsible for all the Pod and container-related operations.

Container runtimes used to be hard-coded in Kubernetes, but with the development of CRI, Kubernetes is more flexible now and uses different container runtimes without the need to recompile. Any container runtime that implements CRI can be used by Kubernetes to manage Pods, containers, and container images.

In the next section, we will discuss some of the CRI shims.