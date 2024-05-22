# K8s Concepts

- [K8s Concepts](#k8s-concepts)
  - [Cluster Architecture](#cluster-architecture)
    - [Kubernetes Components](#kubernetes-components)
      - [Nodes](#nodes)
      - [Controllers](#controllers)
    - [Garbage Collection](#garbage-collection)
  - [Configuration and Object Management](#configuration-and-object-management)
    - [Best Practice](#best-practice)
    - [Imperative Vs Declarative Management](#imperative-vs-declarative-management)
    - [Kubeconfig](#kubeconfig)
    - [ConfigMaps \& Secrets](#configmaps--secrets)
    - [Configure Pods, Containers \& Deployments](#configure-pods-containers--deployments)
    - [Labels \& Annotations](#labels--annotations)
  - [RBAC](#rbac)
  - [Workloads](#workloads)
    - [Pods](#pods)
      - [Init Containers](#init-containers)
      - [Sidecar Containers](#sidecar-containers)
      - [Pause Container](#pause-container)
    - [Workload Management](#workload-management)
      - [Jobs and Cronjobs](#jobs-and-cronjobs)
      - [DaemonSets](#daemonsets)
  - [Services, Load Balancing, and Networking](#services-load-balancing-and-networking)
    - [Services](#services)
    - [Network Policies](#network-policies)
      - [Service Types](#service-types)
      - [Headless Service](#headless-service)
    - [Ingress](#ingress)
  - [Scheduling, Preemption and Eviction](#scheduling-preemption-and-eviction)
  - [Extending Kubernetes](#extending-kubernetes)
    - [Custom Resources](#custom-resources)
      - [Extending the Kubernetes API](#extending-the-kubernetes-api)
      - [Operator Patterns](#operator-patterns)
    - [Istio and Envoy](#istio-and-envoy)
  - [Cloud K8s Services](#cloud-k8s-services)
  - [Troubleshooting](#troubleshooting)

## Cluster Architecture

* [k8s Docs - Cluster Architecture](https://kubernetes.io/docs/concepts/architecture/)

### Kubernetes Components

Detailed information can be found [here](https://kubernetes.io/docs/concepts/overview/components/).

| Name                                                                                                      | Short Name | Cluster Component |
| :-------------------------------------------------------------------------------------------------------- | :--------- | :---------------- |
| [etcd](https://etcd.io/docs/)                                                                             | n/a        | Control Plane     |
| [API Server](https://kubernetes.io/docs/reference/command-line-tools-reference/kube-apiserver/)           | api        | Control Plane     |
| [Controller Manager](https://kubernetes.io/docs/concepts/architecture/controller/)                        | c-m        | Control Plane     |
| [Cloud Controller Manager (Optional)](https://kubernetes.io/docs/concepts/architecture/cloud-controller/) | c-c-m      | Control Plane     |
| [Scheduler](https://kubernetes.io/docs/concepts/scheduling-eviction/kube-scheduler/)                      | sched      | Control Plane     |
| [kubelet](https://kubernetes.io/docs/reference/command-line-tools-reference/kubelet/)                     | n/a        | Node              |
| [kube-proxy](https://kubernetes.io/docs/reference/command-line-tools-reference/kube-proxy/)               | k-proxy    | Node              |
| [Container runtime interface](https://kubernetes.io/docs/concepts/architecture/cri/)                      | n/a        | Node              |

#### Nodes

* [Nodes](https://kubernetes.io/docs/concepts/architecture/nodes/)

#### Controllers

* [k8s Docs - Controllers](https://kubernetes.io/docs/concepts/architecture/controller/)

### Garbage Collection

* [Garbage Collection](https://kubernetes.io/docs/concepts/architecture/garbage-collection/)

## Configuration and Object Management

### Best Practice

* [k8s Docs - Configuration Best Practices](https://kubernetes.io/docs/concepts/configuration/overview/)

### Imperative Vs Declarative Management

* [k8s Docs - Imperative Management of Kubernetes Objects Using Configuration Files](https://kubernetes.io/docs/tasks/manage-kubernetes-objects/imperative-config/)
* [k8s Docs - Declarative Management of Kubernetes Objects Using Configuration Files](https://kubernetes.io/docs/tasks/manage-kubernetes-objects/declarative-config/)

### Kubeconfig

The default path for the kubeconf file is ```$HOME/.kube/config```.

* [k8s Docs - Organizing Cluster Access Using kubeconfig Files](https://kubernetes.io/docs/concepts/configuration/organize-cluster-access-kubeconfig/)
* [Medium Article by Claire Lee - Kubeconfig](https://yuminlee2.medium.com/kubernetes-kubeconfig-file-4aabe3b04ade#4890)

### ConfigMaps & Secrets

* [ConfigMaps](https://kubernetes.io/docs/concepts/configuration/configmap/)
* [Secrets](https://kubernetes.io/docs/concepts/configuration/secret/)

### Configure Pods, Containers & Deployments

* [Jack Dwyer - Kubernetes Deployment Vs Pod:](https://zeet.co/blog/kubernetes-deployment-vs-pod#what-is-a-kubernetes-deployment)
* [k8s Docs - Liveness, Readiness and Startup Probes](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/)

### Labels & Annotations

* [k8s Docs - Recommended Labels](https://kubernetes.io/docs/concepts/overview/working-with-objects/common-labels/)
* [K8s Docs - Annotations](https://kubernetes.io/docs/concepts/overview/working-with-objects/annotations/)

## RBAC

* [k8s Docs - User Accounts Vs Service Accounts](https://kubernetes.io/docs/reference/access-authn-authz/service-accounts-admin/#user-accounts-versus-service-accounts)
* [k8s Docs - Request Verbs](https://kubernetes.io/docs/reference/access-authn-authz/authorization/#determine-the-request-verb)
* [Hack Tricks Cloud - Kubernetes Role-Based Access Control(RBAC)](https://cloud.hacktricks.xyz/pentesting-cloud/kubernetes-security/kubernetes-role-based-access-control-rbac)

## Workloads

### Pods

#### Init Containers

* [k8s Docs - Init Containers](https://kubernetes.io/docs/concepts/workloads/pods/init-containers/)

#### Sidecar Containers

* [k8s Docs - Sidecar Containers](https://kubernetes.io/docs/concepts/workloads/pods/sidecar-containers/)

#### Pause Container

* [DevOpsSchool - What is Pause container in Kubernetes?](https://www.devopsschool.com/blog/what-is-pause-container-in-kubernetes/)

### Workload Management

#### Jobs and Cronjobs

* [k8s Docs - Jobs](https://kubernetes.io/docs/concepts/workloads/controllers/job/)
* [k8s Docs - Cronjob](https://kubernetes.io/docs/concepts/workloads/controllers/cron-jobs/)
* [Spacelift Docs - What Are Kubernetes Jobs? Use Cases, Types & How to Run](https://spacelift.io/blog/kubernetes-jobs)

#### DaemonSets

* [k8s Docs - DaemonSets](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/)

## Services, Load Balancing, and Networking

### Services

* [YouTube - TechWorld with Nana - Kubernetes Services - ClusterIP vs NodePort vs LoadBalancer vs Headless Service](https://www.youtube.com/watch?v=T4Z7visMM4E&t=11s)
* [k8s Docs - Services](https://kubernetes.io/docs/concepts/services-networking/service/)
* [k8s Docs - Defining a Service](https://kubernetes.io/docs/concepts/services-networking/service/#defining-a-service)
* [k8s Docs - Use a Service to Access an Application in a Cluster](https://kubernetes.io/docs/tasks/access-application-cluster/service-access-application-cluster/)
* [k8s Docs - Service Configuratio File](https://kubernetes.io/docs/concepts/services-networking/service/)

### Network Policies

* [YouTube - TechWorld with Nana - Kubernetes Networking - Container Communication inside the Pod](https://www.youtube.com/watch?v=5cNrTU6o3Fw&t=11s)
* [k8s Docs - Network Policies](https://kubernetes.io/docs/concepts/services-networking/network-policies/)
* [GitHub - The Container Network Interface (cni)](https://github.com/containernetworking/cni)

#### Service Types

| Service Type                                                                                  | Description                                              |
| :-------------------------------------------------------------------------------------------- | :------------------------------------------------------- |
| [ClusterIP](https://kubernetes.io/docs/concepts/services-networking/service/#type-clusterip)  | This is the default type for a service.                  |
| [NodePort](https://kubernetes.io/docs/concepts/services-networking/service/#type-nodeport)    | Dedicated port on each node.                             |
| [LoadBalancer](https://kubernetes.io/docs/concepts/services-networking/service/#loadbalancer) | Extension of NodePort utilising third part load balancer |
| [ExternalName](https://kubernetes.io/docs/concepts/services-networking/service/#externalname) |                                                          |

#### Headless Service

* [k8s Docs - Headless Service (With and Without Selectors)](https://kubernetes.io/docs/concepts/services-networking/service/#headless-services)

### Ingress

* [YouTube - TechWorld with Nana - Kubernetes Ingress Tutorial](https://www.youtube.com/watch?v=80Ew_fsV4rM&list=PLy7NrYWoggjziYQIDorlXjTvvwweTYoNC&index=10)
* [k8s Docs - Ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/#load-balancing)
* [k8s Docs - Ingress Controllers](https://kubernetes.io/docs/concepts/services-networking/ingress-controllers/)

## Scheduling, Preemption and Eviction

* [k8s Docs - Pod Topology Spread Constraints](https://kubernetes.io/docs/concepts/scheduling-eviction/topology-spread-constraints/)

## Extending Kubernetes

### Custom Resources

#### Extending the Kubernetes API

* [Custom Resources](https://kubernetes.io/docs/concepts/extend-kubernetes/api-extension/custom-resources/)

#### Operator Patterns

* [YouTube - TechWorld with Nana - Kubernetes Operator Simply Explained](https://www.youtube.com/watch?v=ha3LjlD6g7g&list=PLy7NrYWoggjw0OMxUDIImjWQjM7qZWn_R)
* [k8s Docs - Operator Patterns](https://kubernetes.io/docs/concepts/extend-kubernetes/operator/)
* [OperatorHub](https://operatorhub.io/)
* [Operator SDK](https://sdk.operatorframework.io/)
* [Operator SDK - Operator Scope](https://sdk.operatorframework.io/docs/building-operators/golang/operator-scope/)
* [GitHub - Operator SKD](https://github.com/operator-framework/operator-sdk)

### Istio and Envoy

* [Istio Docs - Architecture](https://istio.io/latest/docs/ops/deployment/architecture/)
* [Envoy Docs](https://www.envoyproxy.io/)

## Cloud K8s Services 

* [AWS EKS (Elastic Kubernetes Service)](https://docs.aws.amazon.com/eks/latest/userguide/what-is-eks.html)
* [GCP GKE (Google Kubernetes Engine)](https://cloud.google.com/kubernetes-engine)
* [Azure AKS (Azure Kubernetets Service)](https://azure.microsoft.com/en-us/products/kubernetes-service)

## Troubleshooting

* [Troubleshooting Applications](https://kubernetes.io/docs/tasks/debug/debug-application/)