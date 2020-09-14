---
title: "What Are Containers?"
permalink: /course/chapter-2/what-are-containers
---
Before we dive into container orchestration, let's review first what containers are.

**Containers** are application-centric methods to deliver high-performing, scalable applications on any infrastructure of your choice. Containers are best suited to deliver microservices by providing portable, isolated virtual environments for applications to run without interference from other running applications.

{% include figure image_path="/assets/images/Ch_2_-_Containers_-_why_containers.png" alt="Containers bundle applications and libraries" caption="Containers" %}

**Microservices** are lightweight applications written in various modern programming languages, with specific dependencies, libraries and environmental requirements. To ensure that an application has everything it needs to run successfully it is packaged together with its dependencies.

Containers encapsulate microservices and their dependencies but do not run them directly. Containers run container images.

A **container image** bundles the application along with its runtime and dependencies, and a container is deployed from the container image offering an isolated executable environment for the application. Containers can be deployed from a specific image on many platforms, such as workstations, Virtual Machines, public cloud, etc.