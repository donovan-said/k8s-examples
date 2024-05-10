# Concepts

- [Concepts](#concepts)
  - [Cluster Architecture](#cluster-architecture)
    - [Kubernetes Components](#kubernetes-components)
      - [Control Plane](#control-plane)
      - [Node](#node)
  - [Kubeconfig](#kubeconfig)
  - [Imperative Vs Declarative Management](#imperative-vs-declarative-management)
  - [Load Balancing](#load-balancing)
  - [Cloud K8s Services](#cloud-k8s-services)

## Cluster Architecture

* [k8s Docs - Cluster Architecture](https://kubernetes.io/docs/concepts/architecture/)
* [k8s Docs - Nodes](https://kubernetes.io/docs/concepts/architecture/nodes/)
* [k8s Docs - Nodes and the Control Plane Communication](https://kubernetes.io/docs/concepts/architecture/control-plane-node-communication/)

### Kubernetes Components

Detailed information can be found [here](https://kubernetes.io/docs/concepts/overview/components/).

#### Control Plane

* etcd
* API Server aka api
* Controller Manager aka c-m
* Cloud Controller Manager aka c-c-m (Optional)
* Scheduler aka sched

#### Node

* kubelet
* kube-proxy aka k-proxy

## Kubeconfig

The default path for the kubeconf file is ```$HOME/.kube/config```.

* [k8s Docs - Organizing Cluster Access Using kubeconfig Files](https://kubernetes.io/docs/concepts/configuration/organize-cluster-access-kubeconfig/)
* [Medium Article by Claire Lee - Kubeconfig](https://yuminlee2.medium.com/kubernetes-kubeconfig-file-4aabe3b04ade#4890)

## Imperative Vs Declarative Management

* [k8s Docs - Imperative Management of Kubernetes Objects Using Configuration Files](https://kubernetes.io/docs/tasks/manage-kubernetes-objects/imperative-config/)
* [k8s Docs - Declarative Management of Kubernetes Objects Using Configuration Files](https://kubernetes.io/docs/tasks/manage-kubernetes-objects/declarative-config/)

## Load Balancing

* [k8s Docs - Ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/#load-balancing)

## Cloud K8s Services 

* AWS EKS (Elastic Kubernetes Service)
* GCP GKE (Google Kubernetes Engine)
* Azure AKS (Azure Kubernetets Service)