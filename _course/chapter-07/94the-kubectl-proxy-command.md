---
title: "The 'kubectl proxy' Command"
permalink: /course/chapter-7/the-kubectl-proxy-command
---
Issuing the `kubectl proxy` command, `kubectl` authenticates with the API server on the master node and makes the Dashboard available on a slightly different URL than the one earlier, this time through the proxy port 8001.

First, we issue the `kubectl proxy` command:

```shell
$ kubectl proxy
Starting to serve on 127.0.0.1:8001
```

It locks the terminal for as long as the proxy is running. With the **proxy** running we can access the **Dashboard** over the new URL (just click on it below - it should work on your workstation). Once we stop the proxy (with CTRL + C) the Dashboard is no longer accessible.

`http://127.0.0.1:8001/api/v1/namespaces/kube-system/services/kubernetes-dashboard:/proxy/#!/overview?namespace=default`

{% include figure image_path="/assets/images/Chpater6_-_Image_2_-_Kubernetes_Dashboard.png" alt="Accessing the Kubernetes dashboard" caption="Kubernetes Dashboard over the proxy"%}