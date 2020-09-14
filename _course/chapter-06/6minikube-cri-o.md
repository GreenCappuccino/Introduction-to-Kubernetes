---
title: "Minikube CRI-O"
permalink: /course/chapter-6/minikube-cri-o
---
According to the [CRI-O website](http://cri-o.io/),

*"CRI-O is an implementation of the Kubernetes CRI (Container Runtime Interface) to enable using OCI (Open Container Initiative) compatible runtimes."*

**Start Minikube with CRI-O as container runtime, instead of Docker, with the following command:**

```shell
$ minikube start --container-runtime=cri-o
minikube v1.0.1 on linux (amd64)
Downloading Kubernetes v1.14.1 images in the background ...
Tip: Use 'minikube start -p <name>' to create a new cluster, or 'minikube delete' to delete this one.
Restarting existing virtualbox VM for "minikube" ...
Waiting for SSH access ...
"minikube" IP address is 192.168.99.100
Configuring CRI-O as the container runtime ...
Version of container runtime is 1.13.5
Waiting for image downloads to complete ...
Preparing Kubernetes environment ...
Pulling images required by Kubernetes v1.14.1 ...
Relaunching Kubernetes v1.14.1 using kubeadm ... 
Waiting for pods: apiserver etcd scheduler controller
Updating kube-proxy configuration ...
Verifying component health ......
kubectl is now configured to use "minikube"
For best results, install kubectl: https://kubernetes.io/docs/tasks/tools/install-kubectl/
Done! Thank you for using minikube!
```

**Let's login via ssh into the Minikube's VM:**

```shell
$ minikube ssh
                         _             _
            _         _ ( )           ( )
  ___ ___  (_)  ___  (_)| |/')  _   _ | |_      __
/' _ ` _ `\| |/' _ `\| || , <  ( ) ( )| '_`\  /'__`\
| ( ) ( ) || || ( ) || || |\`\ | (_) || |_) )(  ___/
(_) (_) (_)(_)(_) (_)(_)(_) (_)`\___/'(_,__/'`\____)

$ _
```

**NOTE: If you try to list containers using the `docker` command, it will not produce any results, because Docker is not running containers:**
{:.notice--info}

```shell
$ sudo docker container ls
Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running?
```

**List the containers created via CRI-O container runtime with the following command:**

```shell
$ sudo runc list
ID                                                                 PID         STATUS      BUNDLE                                                                                                                 CREATED                          OWNER 
1090869caeea44cb179d31b70ba5b6de96f10a8a5f4286536af5dac1c4312030   3661        running     /run/containers/storage/overlay-containers/1090869caeea44cb179d31b70ba5b6de96f10a8a5f4286536af5dac1c4312030/userdata   2019-04-18T20:03:02.199284303Z   root
1e9f8dce6d535b67822e744204098060ff92e574780a1809adbda48ad8605d06   3614        running     /run/containers/storage/overlay-containers/1e9f8dce6d535b67822e744204098060ff92e574780a1809adbda48ad8605d06/userdata   2019-04-18T20:03:02.129881761Z   root
1edcfc78bca52be153cc9f525d9fc64be75ccea478897004a5032f37c6c4c9dc   3812        running     /run/containers/storage/overlay-containers/1edcfc78bca52be153cc9f525d9fc64be75ccea478897004a5032f37c6c4c9dc/userdata   2019-04-18T20:03:02.740669541Z   root
...
```