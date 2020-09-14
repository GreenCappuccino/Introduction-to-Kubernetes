---
title: "Master Node Components: etcd"
permalink: /course/chapter-4/master-node-components-etcd
---
**etcd** is a distributed key-value data store used to persist a Kubernetes cluster's state. New data is written to the data store only by appending to it, data is never replaced in the data store. Obsolete data is compacted periodically to minimize the size of the data store.

Out of all the control plane components, only the API server is able to communicate with the etcd data store.

etcd's CLI management tool provides backup, snapshot, and restore capabilities which come in handy especially for a single etcd instance Kubernetes cluster - common in Development and learning environments. However, in Stage and Production environments, it is extremely important to replicate the data stores in HA mode, for cluster configuration data resiliency.

Some Kubernetes cluster bootstrapping tools, by default, provision stacked etcd master nodes, where the data store runs alongside and shares resources with the other control plane components on the same master node. For data store isolation from the control plane components, the bootstrapping process can be configured for an external etcd, where the data store is provisioned on a dedicated separate host, thus reducing the chances of an etcd failure. Both stacked and external etcd configurations support HA configurations. etcd is based on the [Raft Consensus Algorithm](https://web.stanford.edu/~ouster/cgi-bin/papers/raft-atc14) which allows a collection of machines to work as a coherent group that can survive the failures of some of its members. At any given time, one of the nodes in the group will be the master, and the rest of them will be the followers. Any node can be treated as a master.

{% include figure image_path="/assets/images/Master_and_Followers.png" alt="Master and Followers" caption="Master and Followers"%}

etcd is written in the Go programming language. In Kubernetes, besides storing the cluster state, etcd is also used to store configuration details such as subnets, ConfigMaps, Secrets, etc.