---
title: "kubectl"
permalink: /course/chapter-7/kubectl
---
`kubectl` is generally installed before installing Minikube, but we can also install it after. Once installed, `kubectl` receives its configuration automatically for Minikube Kubernetes cluster access. However, in other Kubernetes cluster setups, we may need to configure the cluster access points and certificates required by `kubectl` to access the cluster.

There are different methods that can be used to install `kubectl`, which are mentioned in the [Kubernetes documentation](https://kubernetes.io/docs/tasks/tools/install-kubectl/). For best results, it is recommended to keep `kubectl` at the same version with the Kubernetes run by Minikube - at the time the course was written the latest stable release was **v1.14.1**. Next, we will look at a few steps to install it on Linux, macOS, and Windows systems.