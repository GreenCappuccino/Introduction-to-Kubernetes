---
title: "Accessing Minikube: APIs"
permalink: /course/chapter-7/accessing-minikube-apis
---
As we know, Kubernetes has the **API server**, and operators/users connect to it from the external world to interact with the cluster. Using both CLI and Web UI, we can connect to the API server running on the master node to perform different operations. We can directly connect to the API server using its API endpoints and send commands to it, as long as we can access the master node and have the right credentials.

Below, we can see a part of the HTTP API space of Kubernetes:

{% include figure image_path="/assets/images/api-server-space_.jpg" alt="API Server Space" caption="HTTP API Space of Kubernetes"%}

HTTP API space of Kubernetes can be divided into three independent groups:

-   **Core Group** (`/api/v1`)\
    This group includes objects such as Pods, Services, nodes, namespaces, configmaps, secrets, etc.
-   **Named Group**\
    This group includes objects in `/apis/$NAME/$VERSION` format. These different API versions imply different levels of stability and support:\
    *Alpha level* - it may be dropped at any point in time, without notice. For example, `/apis/batch/v2alpha1`.\
    *Beta level* - it is well-tested, but the semantics of objects may change in incompatible ways in a subsequent beta or stable release. For example, `/apis/certificates.k8s.io/v1beta1`.\
    *Stable level* - appears in released software for many subsequent versions. For example, `/apis/networking.k8s.io/v1`.
-   **System-wide**\
    This group consists of system-wideAPI endpoints, like `/healthz`, `/logs`, `/metrics`, `/ui`, etc.

We can either connect to an API server directly via calling the respective API endpoints or via the CLI/Web UI.

Next, we will see how we can access the Minikube environment we set up in the previous chapter.