---
title: "Installing Minikube on macOS"
permalink: /course/chapter-6/installing-minikube-on-macos
---
Let's learn how to install Minikube v1.0.1 on Mac OS X with VirtualBox v6.0 specifically.

**NOTE: For other versions, the installation steps may vary! Check the [Minikube installation](https://kubernetes.io/docs/tasks/tools/install-minikube/)!**
{:.notice--info}

Although VirtualBox is the default hypervisor for Minikube, on Mac OS X we can configure Minikube at startup to use another hypervisor, with the `--vm-driver=xhyve` or `=hyperkit` start option.

**Install the [VirtualBox](https://www.virtualbox.org/wiki/Downloads) hypervisor for OS X hosts**\
Download and install the `.dmg` package.

**Install Minikube**\
We can download the latest release from the [Minikube release page](https://github.com/kubernetes/minikube/releases). At the time the course was written, the latest Minikube release was v1.0.1. Once downloaded, we need to make it executable and add it to our `PATH`:

```zsh
$ curl -Lo minikube https://storage.googleapis.com/minikube/releases/v1.0.1/minikube-darwin-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/
```

**NOTE:** Replacing `/v1.0.1/` with `/latest/` will always download the latest version.
{:.notice--info}

**Start Minikube**\
We can start Minikube with the `minikube start` command (disregard "Unable to read.../docker/config..." and "No matching credentials..." warnings):

```zsh
$ minikube start
minikube v1.0.1 on darwin (amd64)
Downloading Kubernetes v1.14.1 images in the background ...
Creating virtualbox VM (CPUs=2, Memory=2048MB, Disk=20000MB) ...
Downloading Minikube ISO ...
142.88 MB / 142.88 MB [============================================] 100.00% 0s
"minikube" IP address is 192.168.99.100
Configuring Docker as the container runtime ...
Version of container runtime is 18.06.3-ce
Waiting for image downloads to complete ...
Preparing Kubernetes environment ...
Downloading kubeadm v1.14.1
Downloading kubelet v1.14.1
Pulling images required by Kubernetes v1.14.1 ...
Launching Kubernetes v1.14.1 using kubeadm ... 
Waiting for pods: apiserver proxy etcd scheduler controller dns
Configuring cluster permissions ...
Verifying component health .....
kubectl is now configured to use "minikube"
For best results, install kubectl: https://kubernetes.io/docs/tasks/tools/install-kubectl/
Done! Thank you for using minikube!
```

**Check the status**\
With the `minikube status` command, we display the status of Minikube:

```zsh
$ minikube status
host: Running
kubelet: Running
apiserver: Running
kubectl: Correctly Configured: pointing to minikube-vm at 192.168.99.100
```

**Stop minikube**\
With the `minikube stop` command, we can stop Minikube:

```zsh
$ minikube stop
Stopping "minikube" in virtualbox ...
"minikube" stopped.
```