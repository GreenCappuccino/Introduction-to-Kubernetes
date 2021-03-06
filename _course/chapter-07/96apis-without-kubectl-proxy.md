---
title: "APIs - without 'kubectl proxy'"
permalink: /course/chapter-7/apis-without-kubectl-proxy
---
When not using the `kubectl proxy`, we need to authenticate to the API server when sending API requests. We can authenticate by providing a **Bearer Token** when issuing a `curl`, or by providing a set of **keys** and **certificates**.

A **Bearer Token** is an **access token** which is generated by the authentication server (the API server on the master node) and given back to the client. Using that token, the client can connect back to the Kubernetes API server without providing further authentication details, and then, access resources.

**Get the token:**

```shell
$ TOKEN=$(kubectl describe secret -n kube-system $(kubectl get secrets -n kube-system | grep default | cut -f1 -d ' ') | grep -E '^token' | cut -f2 -d':' | tr -d '\t' | tr -d " ")
```

**Get the API server endpoint:**

```shell
$ APISERVER=$(kubectl config view | grep https | cut -f 2- -d ":" | tr -d " ")
```

**Confirm that the `APISERVER` stored the same IP as the Kubernetes master IP by issuing the following 2 commands and comparing their outputs:**

```shell
$ echo $APISERVER
https://192.168.99.100:8443
```

```shell
$ kubectl cluster-info
Kubernetes master is running at https://192.168.99.100:8443 ...
```

**Access the API server using the `curl` command, as shown below:**

```shell
$ curl $APISERVER --header "Authorization: Bearer $TOKEN" --insecure
{
 "paths": [
   "/api",
   "/api/v1",
   "/apis",
   "/apis/apps",
   ......
   ......
   "/logs",
   "/metrics",
   "/openapi/v2",
   "/version"
 ]
}
```

Instead of the `access token`, we can extract the client certificate, client key, and certificate authority data from the `.kube/config` file. Once extracted, they are encoded and then passed with a `curl` command for authentication. The new `curl` command looks similar to:

```shell
$ curl $APISERVER --cert encoded-cert --key encoded-key --cacert encoded-ca
```