---
title: "Kubernetes Configuration"
permalink: /course/chapter-5/kubernetes-configuration
---
Kubernetes can be installed using different configurations. The four major installation types are briefly presented below:

-   **All-in-One Single-Node Installation**\
    In this setup, all the master and worker components are installed and running on a single-node. While it is useful for learning, development, and testing, it should not be used in production. Minikube is one such example, and we are going to explore it in future chapters.
-   **Single-Node etcd, Single-Master and Multi-Worker Installation**\
    In this setup, we have a single-master node, which also runs a single-node etcd instance. Multiple worker nodes are connected to the master node.
-   **Single-Node etcd, Multi-Master and Multi-Worker Installation**\
    In this setup, we have multiple-master nodes configured in HA mode, but we have a single-node etcd instance. Multiple worker nodes are connected to the master nodes.
-   **Multi-Node etcd, Multi-Master and Multi-Worker Installation**\
    In this mode, etcd is configured in clustered HA mode, the master nodes are all configured in HA mode, connecting to multiple worker nodes. This is the most advanced and recommended production setup.