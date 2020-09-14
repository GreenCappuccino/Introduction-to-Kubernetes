---
title: "Worker Node Components: kubelet - CRI shims"
permalink: /course/chapter-4/worker-node-components-kubelet-cri-shims
---
Below you will find some examples of CRI shims:

-   **dockershim**\
    With dockershim, containers are created using Docker installed on the worker nodes. Internally, Docker uses containerd to create and manage containers.

{% include figure image_path="/assets/images/dockershim.png" alt="dockershim" caption="dockershim (Retrieved from [blog.kubernetes.io](http://blog.kubernetes.io/2017/11/containerd-container-runtime-options-kubernetes.html))"%}

-   **cri-containerd**\
    With cri-containerd, we can directly use Docker's smaller offspring containerd to create and manage containers.

{% include figure image_path="/assets/images/cri-containerd.png" alt="cri-containerd" caption="cri-containerd (Retrieved from [blog.kubernetes.io](http://blog.kubernetes.io/2017/11/containerd-container-runtime-options-kubernetes.html))"%}

-   **CRI-O**\
    CRI-O enables using any Open Container Initiative (OCI) compatible runtimes with Kubernetes. At the time this course was created, CRI-O supported runC and Clear Containers as container runtimes. However, in principle, any OCI-compliant runtime can be plugged-in.

{% include figure image_path="/assets/images/crio.png" alt="cri-o" caption="CRI-O (Retrieved from [cri-o.io](http://cri-o.io/))"%}