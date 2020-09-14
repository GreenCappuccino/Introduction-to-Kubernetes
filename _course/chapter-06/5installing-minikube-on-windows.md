---
title: "Installing Minikube on Windows"
permalink: /course/chapter-6/installing-minikube-on-windows
---
Let's learn how to install Minikube 1.0.1 on Windows 10 with VirtualBox v6.0.6 specifically.

**NOTE: For other versions, the installation steps may vary! Check the [Minikube installation](https://kubernetes.io/docs/tasks/tools/install-minikube/)!**
{:.notice--info}

**NOTE:** Windows support is currently in experimental phase, and you may encounter issues during installation.
{:.notice--info}

**Install the [VirtualBox](https://www.virtualbox.org/wiki/Downloads) hypervisor for Windows hosts**\
Download and install the `.exe` package.

**NOTE:** Make sure Hyper-V is _disabled_{:.underline} (if prior installed and used) while running VirtualBox.
{:.notice--info}

**Install Minikube**\
We can download the latest release from the [Minikube release page](https://github.com/kubernetes/minikube/releases). At the time the course was written, the latest Minikube release was v1.0.1. Once downloaded, we need to make sure it is added to our `PATH`.

There are two `.exe` packages available to download for Windows found under Minikube v1.0.1:

-   `minikube-windows-amd64.exe` which requires to be added to the `PATH:` manually
-   `minikube-installer.exe` which automatically adds the executable to the `PATH`. 

Download and install the `minikube-installer.exe` package found under Minikube v1.0.1. 

**Start Minikube**\
We can start Minikube using the `minikube start` command (disregard the "Unable to read...docker\\config..." and "No matching credentials..." warnings). Open the PowerShell using the *Run as Administrator* option and execute the following command:

```batch
PS C:\WINDOWS\system32> minikube start
minikube v1.0.1 on windows (amd64)
Downloading Kubernetes v1.14.1 images in the background ...
Creating virtualbox VM (CPUs=2, Memory=2048MB, Disk=20000MB) ...
Downloading Minikube ISO ...
 0 B / 142.88 MB [-----------------------------------------------------]   0.00%
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
We can see the status of Minikube using the `minikube status` command. Open the PowerShell using the *Run as Administrator* option and execute the following command:

```batch
PS C:\WINDOWS\system32> minikube status
host: Running
kubelet: Running
apiserver: Running
kubectl: Correctly Configured: pointing to minikube-vm at 192.168.99.100
```

**Stop Minikube**\
We can stop Minikube using the `minikube stop` command. Open the PowerShell using the *Run as Administrator* option and execute the following command:

```batch
PS C:\WINDOWS\system32> minikube stop
Stopping "minikube" in virtualbox ...
"minikube" stopped.
```