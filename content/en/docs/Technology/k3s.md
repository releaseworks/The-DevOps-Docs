---
title: "k3s"
date: 2017-01-05
weight: 4
description: >
  K3s is a lightweight Kubernetes distribution designed for IoT and resource constrained environments. It's lightweight footprint also makes it perfect for development and testing environments"
---

Kubernetes has become the default  orchestration tool for large scale containerised workloads, however not all containerised workloads require such a heavyweight cluster. For development, proof of concept and testing workloads k3s can provide you with a fully Kubernetes compliant environment without the need for a multinode cluster.

### Installing k3s
Installing k3s on a systemd based linux distribution simply run
```
curl -sfL https://get.k3s.io | sh -
```
If curling scripts into bash makes you uncomfortable you can curl it to a file and inspect it before you running.

k3s is automatically set to start on boot and the installation includes management tools like kubectl and a removal script. Kubectl is available to use immediatly via a kubeconfig file written to `/etc/rancher/k3s/k3s.yaml`.

### Accessing kubectl outside the cluster

By taking a copy of the kubeconfig in `/etc/rancher/k3s/k3s.yaml` and replacing localhost with the ip address of the remote cluster you can manage your k3s cluster remotely. This may be useful if you are using k3s as a remote development cluster.

### Helm 3
As Helm 3 no longer requires tiller k3s and H3lm are best of friends and no additional configuration is required.


### k3s as a PoC development environment

While k3s is not a full cluster and if your production environment targets a full cluster then you must test your application against a full Kubernetes implementation. In proof of concept phases however targetting Kubernetes for a final environment k3s can provide you with a complete Kubernetes api to check your application is working the way you intended it to.