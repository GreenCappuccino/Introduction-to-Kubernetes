---
title: "Kubernetes Dashboard"
permalink: /course/chapter-7/kubernetes-dashboard
---
As mentioned earlier, the [Kubernetes Dashboard](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) provides a web-based user interface for Kubernetes cluster management. To access the dashboard from Minikube, we can use the `minikube dashboard` command, which opens a new tab on our web browser, displaying the Kubernetes Dashboard:

```shell
$ minikube dashboard
```

{% include figure image_path="/assets/images/Chapter_6_-_Image_1_-_Kubernetes_Dashboard.png" alt="Kubernetes dashboard" caption="Kubernetes Dashboard"%}

**NOTE:** In case the browser is not opening another tab and does not display the Dashboard as expected, verify the output in your terminal as it may display a link for the Dashboard (together with some Error messages). Copy and paste that link in a new tab of your browser. Depending on your terminal's features you may be able to just click or right-click the link to open directly in the browser. The link may look similar to:
`http://127.0.0.1:37751/api/v1/namespaces/kube-system/services/http:kubernetes-dashboard:/proxy/`
{:.notice--info}

Chances are that the only difference is the PORT number, which above is 37751. Your port number may be different.

After a logout/login or a reboot of your workstation the normal behavior should be expected (where the `minikube dashboard` command directly opens a new tab in your browser displaying the Dashboard).