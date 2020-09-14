---
title: "Networking Challenges"
permalink: /course/chapter-4/networking-challenges
---
Decoupled microservices based applications rely heavily on networking in order to mimic the tight-coupling once available in the monolithic era. Networking, in general, is not the easiest to understand and implement. Kubernetes is no exception - as a containerized microservices orchestrator is needs to address 4 distinct networking challenges:

-   Container-to-container communication inside Pods
-   Pod-to-Pod communication on the same node and across cluster nodes
-   Pod-to-Service communication within the same namespace and across cluster namespaces
-   External-to-Service communication for clients to access applications in a cluster.

All these networking challenges must be addressed before deploying a Kubernetes cluster. Next, we will see how we solve these challenges.