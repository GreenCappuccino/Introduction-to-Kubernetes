---
title: "Installing kubectl on macOS"
permalink: /course/chapter-7/installing-kubectl-on-macos
---
There are two ways to install `kubectl` on macOS: manually and using the Homebrew package manager. Next, we will provide instructions for both methods.

**To manually install `kubectl`, download the latest stable kubectl binary, make it executable and move it to the `PATH` with the following command:**

```zsh
$ curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl && chmod +x kubectl && sudo mv kubectl /usr/local/bin/
```

**NOTE:** To download and setup a specific version of `kubectl` (such as v1.14.1), issue the following command:
{:.notice--info}

```zsh
$ curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.14.1/bin/darwin/amd64/kubectl && chmod +x kubectl && sudo mv kubectl /usr/local/bin/
```

**To install `kubectl` with [Homebrew package manager](https://brew.sh/), issue the following command:**

```zsh
$ brew install kubernetes-cli
```