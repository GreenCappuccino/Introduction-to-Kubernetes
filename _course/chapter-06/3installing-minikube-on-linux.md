---
title: "Installing Minikube on Linux"
permalink: /course/chapter-6/installing-minikube-on-linux
---
Let's learn how to install Minikube v1.0.1 on Ubuntu Linux 18.04 LTS with VirtualBox v6.0 specifically.

**NOTE: For other versions, the installation steps may vary! Check the [Minikube installation](https://kubernetes.io/docs/tasks/tools/install-minikube/)!**
{:.notice--info}

**Install the [VirtualBox](https://www.virtualbox.org/wiki/Linux_Downloads) hypervisor**\
Add the source repository for the **bionic** distribution (Ubuntu 18.04), download and register the public key, update and install:

```bash
$ sudo bash -c 'echo "deb https://download.virtualbox.org/virtualbox/debian bionic contrib" >> /etc/apt/sources.list'
$ wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- | sudo apt-key add -
$ sudo apt-get update
$ sudo apt-get install -y virtualbox-6.0
```

**Install Minikube**\
We can download the latest release from the [Minikube release page](https://github.com/kubernetes/minikube/releases). At the time the course was written, the latest Minikube release was v1.0.1. Once downloaded, we need to make it executable and add it to our `PATH`:

```bash
$ curl -Lo minikube https://storage.googleapis.com/minikube/releases/v1.0.1/minikube-linux-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/
```

**NOTE:** Replacing `/v1.0.1/` with `/latest/` will always download the latest version.
{:.notice--info}

**Start Minikube**\
We can start Minikube with the `minikube start` command (disregard "Unable to read.../docker/config..." and "No matching credentials..." warnings):

```bash
$ minikube start
minikube v1.0.1 on linux (amd64)
Downloading Minikube ISO ...
142.88 MB / 142.88 MB [============================================] 100.00% 0s
Downloading Kubernetes v1.14.1 images in the background ...
Creating virtualbox VM (CPUs=2, Memory=2048MB, Disk=20000MB) ...
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

```bash
$ minikube status
host: Running
kubelet: Running
apiserver: Running
kubectl: Correctly Configured: pointing to minikube-vm at 192.168.99.100
```

**Stop minikube**\
With the `minikube stop` command, we can stop Minikube:

```bash
$ minikube stop
Stopping "minikube" in virtualbox ...
"minikube" stopped.
```