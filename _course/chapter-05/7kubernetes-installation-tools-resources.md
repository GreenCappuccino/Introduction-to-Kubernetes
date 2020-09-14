---
title: "Kubernetes Installation Tools/Resources"
permalink: /course/chapter-5/kubernetes-installation-tools-resources
---
While discussing installation configuration and the underlying infrastructure, let's take a look at some useful tools/resources available:

-   **kubeadm**\
    [kubeadm](https://github.com/kubernetes/kubeadm) is a first-class citizen on the Kubernetes ecosystem. It is a secure and recommended way to bootstrap a single- or multi-node Kubernetes cluster. It has a set of building blocks to setup the cluster, but it is easily extendable to add more features. Please note that kubeadm does not support the provisioning of hosts.
-   **kubespray**\
    With [kubespray](https://kubernetes.io/docs/setup/custom-cloud/kubespray/) (formerly known as kargo), we can install Highly Available Kubernetes clusters on AWS, GCE, Azure, OpenStack, or bare metal. Kubespray is based on Ansible, and is available on most Linux distributions. It is a [Kubernetes Incubator](https://github.com/kubernetes-sigs/kubespray) project.
-   **kops**\
    With [kops](https://kubernetes.io/docs/setup/custom-cloud/kops/), we can create, destroy, upgrade, and maintain production-grade, highly-available Kubernetes clusters from the command line. It can provision the machines as well. Currently, AWS is officially supported. Support for GCE is in beta, and VMware vSphere in alpha stage, and other platforms are planned for the future. Explore the [kops project](https://github.com/kubernetes/kops) for more details.
-   **kube-aws**\
    With [kube-aws](https://github.com/kubernetes-incubator/kube-aws) we can create, upgrade and destroy Kubernetes clusters on AWS from the command line. Kube-aws is also a Kubernetes Incubator project.

If the existing solutions and tools do not fit our requirements, then we can [install Kubernetes from scratch](https://v1-12.docs.kubernetes.io/docs/setup/release/building-from-source/) (although a dated link from Kubernetes v1.12, it is still a valid solution).

It is worth checking out the *[Kubernetes The Hard Way](https://github.com/kelseyhightower/kubernetes-the-hard-way)* GitHub project by [Kelsey Hightower](https://twitter.com/kelseyhightower), which shares the manual steps involved in bootstrapping a Kubernetes cluster.