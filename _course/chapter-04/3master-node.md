---
title: "Master Node"
permalink: /course/chapter-4/master-node
---
The **master node** provides a running environment for the control plane responsible for managing the state of a Kubernetes cluster, and it is the brain behind all operations inside the cluster. The control plane components are agents with very distinct roles in the cluster's management. In order to communicate with the Kubernetes cluster, users send requests to the master node via a Command Line Interface (CLI) tool, a Web User-Interface (Web UI) Dashboard, or Application Programming Interface (API).

{% include figure image_path="/assets/images/Master_Node1.png" alt="Kubernetes Master Node" caption="Kubernetes Master Node"%}

It is important to keep the control plane running at all costs. Losing the control plane may introduce downtimes, causing service disruption to clients, with possible loss of business. To ensure the control plane's fault tolerance, master node replicas are added to the cluster, configured in High-Availability (HA) mode. While only one of the master node replicas actively manages the cluster, the control plane components stay in sync across the master node replicas. This type of configuration adds resiliency to the cluster's control plane, should the active master node replica fail.

To persist the Kubernetes cluster's state, all cluster configuration data is saved to [etcd](https://github.com/etcd-io). However, **etcd** is a distributed key-value store which only holds cluster state related data, no client workload data. etcd is configured on the master node ([stacked](https://kubernetes.io/docs/setup/independent/ha-topology/#stacked-etcd-topology)) or on its dedicated host ([external](https://kubernetes.io/docs/setup/independent/ha-topology/#external-etcd-topology)) to reduce the chances of data store loss by decoupling it from the control plane agents.

When stacked, HA master node replicas ensure etcd resiliency as well. Unfortunately, that is not the case of external etcds, when the etcd hosts have to be separately replicated for HA mode configuration.