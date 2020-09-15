---
title: "Installing kubectl on Windows"
permalink: /course/chapter-7/installing-kubectl-on-windows
---
To install `kubectl`, we can download the binary directly or use `curl` from the CLI. Once downloaded the binary needs to be added to the `PATH`.

**Direct download link for v1.14.1 binary (just click below):**

<https://storage.googleapis.com/kubernetes-release/release/v1.14.1/bin/windows/amd64/kubectl.exe>

**NOTE:** Obtain the latest `kubectl` stable release version number from the link below, and if needed, edit the download link for the binary from above: 

<https://storage.googleapis.com/kubernetes-release/release/stable.txt>

**Use the `curl` command (if installed) from the CLI:**

```shell
$ curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.14.1/bin/windows/amd64/kubectl.exe
```

**Once downloaded, move the `kubectl` binary to the `PATH`.**