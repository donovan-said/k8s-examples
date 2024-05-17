# Grafana Deployment

<p align="center">
    <img src="../../imgs/grafana_logo.png" width="320" height="300"> 
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    <img src="../../imgs/prometheus_logo.png" width="350" height="300">
</p>

## Overview

- [Grafana Deployment](#grafana-deployment)
  - [Overview](#overview)
  - [Guides](#guides)
  - [Prometheus Deployment](#prometheus-deployment)
    - [Clean Up](#clean-up)
  - [Grafana Deployment](#grafana-deployment-1)
    - [Deployment](#deployment)
    - [Validate](#validate)
    - [Access Grafana](#access-grafana)
    - [Clean Up](#clean-up-1)

## Guides

* [Grafana Docs - Monitoring Kubernetes layers: Key metrics to know](https://grafana.com/blog/2023/01/25/monitoring-kubernetes-layers-key-metrics-to-know/)
* [Grafana Docs - Deploy Grafana on Kubernetes Guide](https://grafana.com/docs/grafana/latest/setup-grafana/installation/kubernetes/)
* [Grafana Docs - How to monitor Kubernetes clusters with the Prometheus Operator](https://grafana.com/blog/2023/01/19/how-to-monitor-kubernetes-clusters-with-the-prometheus-operator)

## Prometheus Deployment

* ```kubectl apply -f https://raw.githubusercontent.com/prometheus-operator/prometheus-operator/main/bundle.yaml --force-conflicts=true --server-side=true```
* ```kubectl apply -f example-cluster-management/grafana/prometheus-rbac.yaml```
* ```kubectl apply -f example-cluster-management/grafana/prometheus-instance.yaml```
* ```kubectl port-forward svc/prometheus-operated 9090:9090``` and visit http://localhost:9090/
* ```kubectl apply -f example-cluster-management/grafana/prometheus-service-monitor.yaml```
* ```kubectl apply -f example-cluster-management/grafana/prometheus-service.yaml```

### Clean Up

* ```kubectl delete -f example-cluster-management/grafana/prometheus-service.yaml```
* ```kubectl delete -f example-cluster-management/grafana/prometheus-service-monitor.yaml```
* ```kubectl delete -f example-cluster-management/grafana/prometheus-instance.yaml```
* ```kubectl delete -f example-cluster-management/grafana/prometheus-rbac.yaml```
* ```kubectl delete -f https://raw.githubusercontent.com/prometheus-operator/prometheus-operator/main/bundle.yaml --force-conflicts=true --server-side=true```

## Grafana Deployment

### Deployment

* ```kubectl apply -f example-cluster-management/grafana/grafana-namespace.yaml```
* ```kubectl apply -f example-cluster-management/grafana/grafana-manifest.yaml -n grafana-namespace```

### Validate

* ```kubectl get pvc -n grafana-namespace  -o wide```
* ```kubectl get deployments -n grafana-namespace  -o wide```
* ```kubectl get svc -n grafana-namespace  -o wide```

### Access Grafana

* ```kubectl get all --n grafana-namespace```
* Proceed to access the endpoint [here](http://localhost:3000/).

### Clean Up

* ```kubectl delete -f example-cluster-management/grafana/grafana-manifest.yaml -n grafana-namespace```
* ```kubectl delete -f example-cluster-management/grafana/grafana-namespace.yaml```