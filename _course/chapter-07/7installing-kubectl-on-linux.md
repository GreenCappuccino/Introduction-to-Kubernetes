---
title: "Installing kubectl on Linux"
permalink: /course/chapter-7/installing-kubectl-on-linux
---
To install `kubectl` on Linux, follow the instruction below:

**Download the latest stable `kubectl` binary, make it executable and move it to the `PATH`:**

```bash
$ curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl && chmod +x kubectl && sudo mv kubectl /usr/local/bin/
```

**NOTE:** To download and setup a specific version of `kubectl` (such as v1.14.1), issue the following command:
{:.notice--info}

```bash
$ curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.14.1/bin/linux/amd64/kubectl && chmod +x kubectl && sudo mv kubectl /usr/local/bin/
```