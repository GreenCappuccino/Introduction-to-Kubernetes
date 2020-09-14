---
title: "Cloud Native Computing Foundation (CNCF)"
permalink: /course/chapter-3/cloud-native-computing-foundation-cncf
---
The [Cloud Native Computing Foundation](https://www.cncf.io/) (CNCF) is one of the projects hosted by [the Linux Foundation](https://www.linuxfoundation.org/). CNCF aims to accelerate the adoption of containers, microservices, and cloud-native applications.

{% include figure image_path="/assets/images/logo_cncf.png" alt="CNCF logo"%}

CNCF hosts a multitude of projects, with more to be added in the future. CNCF provides resources to each of the projects, but, at the same time, each project continues to operate independently under its pre-existing governance structure and with its existing maintainers. Projects within CNCF are categorized based on achieved status: Sandbox, Incubating, and Graduated. At the time this course was created, there were six projects with Graduated status and many more still Incubating and in the Sandbox.

Graduated projects:

-   [Kubernetes](https://kubernetes.io/) for container orchestration
-   [Prometheus](https://prometheus.io/) for monitoring
-   [Envoy](https://github.com/envoyproxy/envoy) for service mesh
-   [CoreDNS](https://coredns.io/) for service discovery
-   [containerd](http://containerd.io/) for container runtime
-   [Fluentd](http://www.fluentd.org/) for logging

Incubating projects:

-   [rkt](https://github.com/rkt/rkt) and [CRI-O](https://cri-o.io) for container runtime
-   [Linkerd](https://linkerd.io/) for service mesh
-   [etcd](https://github.com/etcd-io) for key/value store
-   [gRPC](http://www.grpc.io/) for remote procedure call (RPC)
-   [CNI](https://github.com/containernetworking/cni) for networking API
-   [Harbor](https://goharbor.io) for registry
-   [Helm](https://www.helm.sh) for package management
-   [Rook](https://github.com/rook/rook) and [Vitess](http://vitess.io/) for cloud-native storage
-   [Notary](https://github.com/theupdateframework/notary) for security
-   [TUF](https://github.com/theupdateframework/specification) for software updates
-   [NATS](https://nats.io) for messaging
-   [Jaeger](https://github.com/jaegertracing/jaeger) and [OpenTracing](http://opentracing.io/) for distributed tracing
-   [Open Policy Agent](https://www.openpolicyagent.org) for policy.

There are many projects in the CNCF Sandbox geared towards metrics, monitoring, identity, scripting, serverless, nodeless, edge, etc.

As we can see, the CNCF projects cover the entire lifecycle of a cloud-native application, from its execution using container runtimes, to its monitoring and logging. This is very important to meet the CNCF goal.