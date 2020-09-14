---
title: "Requirements for Running Minikube"
permalink: /course/chapter-6/requirements-for-running-minikube
---
Minikube is installed and runs directly on a local Linux, macOS, or Windows workstation. However, in order to fully take advantage of all the features Minikube has to offer, a [Type-2 Hypervisor](https://en.wikipedia.org/wiki/Hypervisor) should be installed on the local workstation, to run in conjunction with Minikube. This does not mean that we need to create any VMs with guest operating systems with this Hypervisor.

Minikube builds all its infrastructure as long as the Type-2 Hypervisor is installed on our workstation. Minikube invokes the Hypervisor to create a single VM which then hosts a single-node Kubernetes cluster. Thus we need to make sure that we have the necessary hardware and software required by Minikube to build its environment. Below we outline the requirements to run Minikube on our local workstation:

-   [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) \
    `kubectl` is a binary used to access and manage any Kubernetes cluster. It is installed separately from Minikube. Since we will install `kubectl` after the Minikube installation, we may see warnings during the Minikube initialization - safe to disregard for the time being, but do keep in mind that we will have to install `kubectl` to be able to manage the Kubernetes cluster. We will explore `kubectl` in more detail in future chapters.
-   Type-2 Hypervisor
    -   On Linux [VirtualBox](https://www.virtualbox.org/wiki/Downloads) or [KVM](https://github.com/kubernetes/minikube/blob/master/docs/drivers.md#kvm2-driver)
    -   On macOS [VirtualBox](https://www.virtualbox.org/wiki/Downloads), [HyperKit](https://github.com/kubernetes/minikube/blob/master/docs/drivers.md#hyperkit-driver), or [VMware Fusion](http://www.vmware.com/products/fusion.html)
    -   On Windows [VirtualBox](https://www.virtualbox.org/wiki/Downloads) or [Hyper-V](https://github.com/kubernetes/minikube/blob/master/docs/drivers.md#hyperv-driver) \

**NOTE:** Minikube supports a `--vm-driver=none` option that runs the Kubernetes components directly on the host OS and not inside a VM. With this option a Docker installation is required and a Linux OS on the local workstation, but no hypervisor installation. If you use `--vm-driver=none`, be sure to specify a [bridge network](https://docs.docker.com/network/bridge/#configure-the-default-bridge-network) for Docker. Otherwise, it might change between network restarts, causing loss of connectivity to your cluster.
{:.notice--info}

-   VT-x/AMD-v virtualization must be enabled on the local workstation in BIOS
-   Internet connection on first Minikube run - to download packages, dependencies, updates and pull images needed to initialize the Minikube Kubernetes cluster. Subsequent runs will require an internet connection only when new Docker images need to be pulled from a container repository or when deployed containerized applications need it. Once an image has been pulled it can be reused without an internet connection.

In this chapter, we use VirtualBox as hypervisor on all three operating systems - Linux, macOS, and Windows, to allow Minikube to provision the VM which hosts the single-node Kubernetes cluster.

Read more about Minikube from the official [Kubernetes documentation](https://kubernetes.io/docs/setup/minikube/) or [GitHub](https://github.com/kubernetes/minikube).