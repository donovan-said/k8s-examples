# Concepts

- [Concepts](#concepts)
  - [Cluster Architecture](#cluster-architecture)
    - [Kubernetes Components](#kubernetes-components)
  - [Configuration](#configuration)
    - [Kubeconfig](#kubeconfig)
  - [Object Management](#object-management)
    - [Imperative Vs Declarative Management](#imperative-vs-declarative-management)
    - [Labels \& Annotations](#labels--annotations)
    - [Configure Pods, Containers \& Deployments](#configure-pods-containers--deployments)
  - [RBAC](#rbac)
  - [Services, Load Balancing, and Networking](#services-load-balancing-and-networking)
  - [Scheduling, Preemption and Eviction](#scheduling-preemption-and-eviction)
  - [Cloud K8s Services](#cloud-k8s-services)
  - [Troubleshooting](#troubleshooting)

## Cluster Architecture

* [k8s Docs - Cluster Architecture](https://kubernetes.io/docs/concepts/architecture/)

### Kubernetes Components

Detailed information can be found [here](https://kubernetes.io/docs/concepts/overview/components/).

| Name                                          | Cluster Component | Cluster Component |
| :--------------------------------------------- | :----------------- | :----------------- |
| etcd                                          | Control Plane     |                   |
| API Server aka api                            | Control Plane     |                   |
| Controller Manager aka c-m                    | Control Plane     |                   |
| Cloud Controller Manager aka c-c-m (Optional) | Control Plane     |                   |
| Scheduler aka sched                           | Control Plane     |                   |
| kubelet                                       | Node              |                   |
| kube-proxy aka k-proxy                        | Node              |                   |

## Configuration

* [ConfigMaps](https://kubernetes.io/docs/concepts/configuration/configmap/)
* [Secrets](https://kubernetes.io/docs/concepts/configuration/secret/)

### Kubeconfig

The default path for the kubeconf file is ```$HOME/.kube/config```.

* [k8s Docs - Organizing Cluster Access Using kubeconfig Files](https://kubernetes.io/docs/concepts/configuration/organize-cluster-access-kubeconfig/)
* [Medium Article by Claire Lee - Kubeconfig](https://yuminlee2.medium.com/kubernetes-kubeconfig-file-4aabe3b04ade#4890)

## Object Management

### Imperative Vs Declarative Management

* [k8s Docs - Imperative Management of Kubernetes Objects Using Configuration Files](https://kubernetes.io/docs/tasks/manage-kubernetes-objects/imperative-config/)
* [k8s Docs - Declarative Management of Kubernetes Objects Using Configuration Files](https://kubernetes.io/docs/tasks/manage-kubernetes-objects/declarative-config/)

### Labels & Annotations

* [k8s Docs - Recommended Labels](https://kubernetes.io/docs/concepts/overview/working-with-objects/common-labels/)
* [K8s Docs - Annotations](https://kubernetes.io/docs/concepts/overview/working-with-objects/annotations/)

### Configure Pods, Containers & Deployments

* [Jack Dwyer - Kubernetes Deployment Vs Pod:](https://zeet.co/blog/kubernetes-deployment-vs-pod#what-is-a-kubernetes-deployment)
* [k8s Docs - Liveness, Readiness and Startup Probes](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/)

## RBAC

* [k8s Docs - User Accounts Vs Service Accounts](https://kubernetes.io/docs/reference/access-authn-authz/service-accounts-admin/#user-accounts-versus-service-accounts)
* [k8s Docs - Request Verbs](https://kubernetes.io/docs/reference/access-authn-authz/authorization/#determine-the-request-verb)
* [Hack Tricks Cloud - Kubernetes Role-Based Access Control(RBAC)](https://cloud.hacktricks.xyz/pentesting-cloud/kubernetes-security/kubernetes-role-based-access-control-rbac)

## Services, Load Balancing, and Networking

* [k8s Docs - Ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/#load-balancing)

## Scheduling, Preemption and Eviction

* [k8s Docs - Pod Topology Spread Constraints](https://kubernetes.io/docs/concepts/scheduling-eviction/topology-spread-constraints/)

## Cloud K8s Services 

* [AWS EKS (Elastic Kubernetes Service)](https://docs.aws.amazon.com/eks/latest/userguide/what-is-eks.html)
* [GCP GKE (Google Kubernetes Engine)](https://cloud.google.com/kubernetes-engine)
* [Azure AKS (Azure Kubernetets Service)](https://azure.microsoft.com/en-us/products/kubernetes-service)

## Troubleshooting

* [Troubleshooting Applications](https://kubernetes.io/docs/tasks/debug/debug-application/)