---
title: "Kubernetes Features II"
permalink: /course/chapter-3/kubernetes-features-ii
---
Some other fully supported Kubernetes features are:

-   **Automated rollouts and rollbacks**\
    Kubernetes seamlessly rolls out and rolls back application updates and configuration changes, constantly monitoring the application's health to prevent any downtime.
-   **Secret and configuration management**\
    Kubernetes manages secrets and configuration details for an application separately from the container image, in order to avoid a re-build of the respective image. Secrets consist of confidential information passed to the application without revealing the sensitive content to the stack configuration, like on GitHub.
-   **Storage orchestration**\
    Kubernetes automatically mounts software-defined storage (SDS) solutions to containers from local storage, external cloud providers, or network storage systems.
-   **Batch execution**\
    Kubernetes supports batch execution, long-running jobs, and replaces failed containers.

There are many other features besides the ones we just mentioned, and they are currently in alpha/beta phase. They will add great value to any Kubernetes deployment once they become stable features. For example, support for role-based access control (RBAC) is stable as of the Kubernetes 1.8 release.