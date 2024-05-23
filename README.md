# K8s Guide & Examples

<p align="center">
    <img src="./imgs/k8s_logo.png" width="350" height="300">
</p>

## Overview

The purpose of this repository is to act as a collation of useful information 
relating to k8s and associated third party services. Essentially, these are my 
study notes.

My main guidelines were (though there are many more reference throughout):
* The official [k8s Documentation](https://kubernetes.io/docs/home/)
* The roadmap defined by [roadmap.sh](https://roadmap.sh/kubernetes)

## Content

- [K8s Guide \& Examples](#k8s-guide--examples)
  - [Overview](#overview)
  - [Content](#content)
  - [Concepts \& Guides](#concepts--guides)
    - [General](#general)
    - [Package Management](#package-management)
    - [Node Management](#node-management)
    - [Ingress Controllers](#ingress-controllers)
  - [Examples](#examples)
    - [Kubeconf](#kubeconf)
    - [Cluster Management](#cluster-management)
    - [Manifests](#manifests)
      - [Applications](#applications)
      - [Jobs \& Cronjobs](#jobs--cronjobs)
    - [Helm](#helm)
  - [Quick Guide to Docs](#quick-guide-to-docs)

## Concepts & Guides

### General 

* [K8s Concepts & Guides](./docs/K8S_CONCEPTS.md)
* [kubectl Common Commands](./docs/KUBECTL_COMMANDS.md)

### Package Management

* [Helm Concepts](./docs/HELM_CONCEPTS.md)

### Node Management

* [Karpenter Concepts](./docs/KARPENTER_CONCEPTS.md)

### Ingress Controllers

* [Ingress Controllers](./docs/INGRESS_CONTROLLERS.md) 

## Examples 

### Kubeconf

* [Example kubeconf](./example-kubeconf/)

### Cluster Management

* [Kubernetes Dashboard](./example-cluster-management/kubernetes-dashboard/STEPS.md)
* [Grafana & Prometheus](./example-cluster-management/grafana-and-prometheus/STEPS.md)

### Manifests

#### Applications

* [Sample Blank Objects](./example-apps/blank-sample-objects/)
* [Sample Application](./example-apps/sample-app/STEPS.md)
* [Sample Sidecar](./example-apps/sample-sidecar/STEPS.md)
* [Nginx](./example-apps/nginx/STEPS.md)

#### Jobs & Cronjobs

* [Sample Job](./example-jobs/sample-cronjob/STEPS.md)
* [Sample Cronjob](./example-jobs/sample-cronjob/STEPS.md)

### Helm

* [Sample Chart](./example-helm-charts/sample-chart/)

## Quick Guide to Docs

* [k8s Docs - Concepts](https://kubernetes.io/docs/concepts/)
* [k8s Docs - Tasks](https://kubernetes.io/docs/tasks/)
* [k8s Docs - Tutorials](https://kubernetes.io/docs/tutorials/)
* [k8s Docs - References](https://kubernetes.io/docs/reference/)
* [k8s Docs - Client Libraries](https://kubernetes.io/docs/reference/using-api/client-libraries/)
* [k8s Docs - kubectl](https://kubernetes.io/docs/reference/kubectl/)
* [k8s Docs - Glossary](https://kubernetes.io/docs/reference/glossary/?)