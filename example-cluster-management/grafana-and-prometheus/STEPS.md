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
  - [Prometheus](#prometheus)
    - [Prometheus Operator Deployment](#prometheus-operator-deployment)
    - [Prometheus Deployment](#prometheus-deployment)
    - [Prometheus Access](#prometheus-access)
    - [Prometheus Clean Up](#prometheus-clean-up)
  - [Grafana Deployment](#grafana-deployment-1)
    - [Grafana Deployment](#grafana-deployment-2)
    - [Grafana Validate](#grafana-validate)
    - [Grafana Access](#grafana-access)
    - [Grafana Clean Up](#grafana-clean-up)

## Guides

* [Grafana Docs - Monitoring Kubernetes layers: Key metrics to know](https://grafana.com/blog/2023/01/25/monitoring-kubernetes-layers-key-metrics-to-know/)
* [Grafana Docs - Deploy Grafana on Kubernetes Guide](https://grafana.com/docs/grafana/latest/setup-grafana/installation/kubernetes/)
* [Grafana Docs - How to monitor Kubernetes clusters with the Prometheus Operator](https://grafana.com/blog/2023/01/19/how-to-monitor-kubernetes-clusters-with-the-prometheus-operator)

## Prometheus

### Prometheus Operator Deployment

* ```kubectl apply -f https://raw.githubusercontent.com/prometheus-operator/prometheus-operator/main/bundle.yaml --force-conflicts=true --server-side=true```
* ```kubectl apply -f example-cluster-management/grafana-and-prometheus/prometheus-operator-manifest.yaml```


### Prometheus Deployment

* ```kubectl apply -f example-cluster-management/grafana-and-prometheus/prometheus-instance.yaml```
* ```kubectl apply -f example-cluster-management/grafana-and-prometheus/prometheus-service-monitor.yaml```
* ```kubectl apply -f example-cluster-management/grafana-and-prometheus/prometheus-service.yaml```

### Prometheus Access

* ```kubectl port-forward svc/prometheus-operated 9090:9090``` 
* Visit http://localhost:9090/

### Prometheus Clean Up

* ```kubectl delete -f example-cluster-management/grafana-and-prometheus/prometheus-service.yaml```
* ```kubectl delete -f example-cluster-management/grafana-and-prometheus/prometheus-service-monitor.yaml```
* ```kubectl delete -f example-cluster-management/grafana-and-prometheus/prometheus-instance.yaml```
* ```kubectl delete -f example-cluster-management/grafana-and-prometheus/prometheus-operator-manifest.yaml```
* ```kubectl delete -f https://raw.githubusercontent.com/prometheus-operator/prometheus-operator/main/bundle.yaml```

## Grafana Deployment

### Grafana Deployment

* ```kubectl apply -f example-cluster-management/grafana-and-prometheus/grafana-manifest.yaml -n grafana-namespace```

### Grafana Validate

* ```kubectl get all --n grafana-namespace```

or

* ```kubectl get pvc -n grafana-namespace  -o wide```
* ```kubectl get deployments -n grafana-namespace  -o wide```
* ```kubectl get svc -n grafana-namespace  -o wide```

### Grafana Access

* Proceed to access the endpoint [here](http://localhost:3000/).

### Grafana Clean Up

* ```kubectl delete -f example-cluster-management/grafana-and-prometheus/grafana-manifest.yaml -n grafana-namespace```