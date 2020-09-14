---
title: "Pod-to-External World Communication"
permalink: /course/chapter-4/pod-to-external-world-communication
---
For a successfully deployed containerized applications running in Pods inside a Kubernetes cluster, it requires accessibility from the outside world. Kubernetes enables external accessibility through **services**, complex constructs which encapsulate networking rules definitions on cluster nodes. By exposing services to the external world with **kube-proxy**, applications become accessible from outside the cluster over a virtual IP.

We will have a complete chapter dedicated to this, so we will dive into this later.