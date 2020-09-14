---
title: "Worker Node"
permalink: /course/chapter-4/worker-node
---
A **worker node** provides a running environment for client applications. Though containerized microservices, these applications are encapsulated in Pods, controlled by the cluster control plane agents running on the master node. Pods are scheduled on worker nodes, where they find required compute, memory and storage resources to run, and networking to talk to each other and the outside world. A Pod is the smallest scheduling unit in Kubernetes. It is a logical collection of one or more containers scheduled together. We will explore them further in later chapters.

{% include figure image_path="/assets/images/Worker_Node.png" alt="Worker Node" caption="Kubernetes Worker Node"%}

Also, to access the applications from the external world, we connect to worker nodes and not to the master node. We will dive deeper into this in future chapters.