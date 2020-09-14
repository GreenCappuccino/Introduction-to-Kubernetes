---
title: "Kubernetes Features I"
permalink: /course/chapter-3/kubernetes-features-i
---
Kubernetes offers a very rich set of features for container orchestration. Some of its fully supported features are:

-   **Automatic bin packing**\
    Kubernetes automatically schedules containers based on resource needs and constraints, to maximize utilization without sacrificing availability.
-   **Self-healing**\
    Kubernetes automatically replaces and reschedules containers from failed nodes. It kills and restarts containers unresponsive to health checks, based on existing rules/policy. It also prevents traffic from being routed to unresponsive containers.
-   **Horizontal scaling**\
    With Kubernetes applications are scaled manually or automatically based on CPU or custom metrics utilization.
-   **Service discovery and Load balancing**\
    Containers receive their own IP addresses from Kubernetes, while it assigns a single Domain Name System (DNS) name to a set of containers to aid in load-balancing requests across the containers of the set.