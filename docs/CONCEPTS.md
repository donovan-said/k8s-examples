# Concepts

- [Concepts](#concepts)
  - [Cluster Architecture](#cluster-architecture)
    - [Kubernetes Components](#kubernetes-components)
      - [Control Plane](#control-plane)
      - [Node](#node)
  - [Configuration](#configuration)
    - [ConfigMap](#configmap)
    - [Secrets](#secrets)
    - [Kubeconfig](#kubeconfig)
  - [Imperative Vs Declarative Management](#imperative-vs-declarative-management)
  - [RBAC](#rbac)
  - [Load Balancing](#load-balancing)
  - [Cloud K8s Services](#cloud-k8s-services)
  - [Troubleshooting](#troubleshooting)

## Cluster Architecture

* [k8s Docs - Cluster Architecture](https://kubernetes.io/docs/concepts/architecture/)

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

## Configuration

### ConfigMap

* [ConfigMaps](https://kubernetes.io/docs/concepts/configuration/configmap/)

### Secrets

* [Secrets](https://kubernetes.io/docs/concepts/configuration/secret/)

### Kubeconfig

The default path for the kubeconf file is ```$HOME/.kube/config```.

* [k8s Docs - Organizing Cluster Access Using kubeconfig Files](https://kubernetes.io/docs/concepts/configuration/organize-cluster-access-kubeconfig/)
* [Medium Article by Claire Lee - Kubeconfig](https://yuminlee2.medium.com/kubernetes-kubeconfig-file-4aabe3b04ade#4890)

## Imperative Vs Declarative Management

* [k8s Docs - Imperative Management of Kubernetes Objects Using Configuration Files](https://kubernetes.io/docs/tasks/manage-kubernetes-objects/imperative-config/)
* [k8s Docs - Declarative Management of Kubernetes Objects Using Configuration Files](https://kubernetes.io/docs/tasks/manage-kubernetes-objects/declarative-config/)

## RBAC

* [k8s Docs - User Accounts Vs Service Accounts](https://kubernetes.io/docs/reference/access-authn-authz/service-accounts-admin/#user-accounts-versus-service-accounts)
* [k8s Docs - Request Verbs](https://kubernetes.io/docs/reference/access-authn-authz/authorization/#determine-the-request-verb)
* [Hack Tricks Cloud - Kubernetes Role-Based Access Control(RBAC)](https://cloud.hacktricks.xyz/pentesting-cloud/kubernetes-security/kubernetes-role-based-access-control-rbac)

## Load Balancing

* [k8s Docs - Ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/#load-balancing)

## Cloud K8s Services 

* [AWS EKS (Elastic Kubernetes Service)](https://docs.aws.amazon.com/eks/latest/userguide/what-is-eks.html)
* [GCP GKE (Google Kubernetes Engine)](https://cloud.google.com/kubernetes-engine)
* [Azure AKS (Azure Kubernetets Service)](https://azure.microsoft.com/en-us/products/kubernetes-service)

## Troubleshooting

* [Troubleshooting Applications](https://kubernetes.io/docs/tasks/debug/debug-application/)