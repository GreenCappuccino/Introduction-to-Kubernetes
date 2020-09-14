---
title: "Container-to-Container Communication Inside Pods"
permalink: /course/chapter-4/container-to-container-communication-inside-pods
---
Making use of the underlying host operating system's kernel features, a container runtime creates an isolated network space for each container it starts. On Linux, that isolated network space is referred to as a **network namespace**. A network namespace is shared across containers, or with the host operating system.

When a Pod is started, a network namespace is created inside the Pod, and all containers running inside the Pod will share that network namespace so that they can talk to each other via localhost.