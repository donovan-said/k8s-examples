# Nginx Ingress Controller

<p align="center">
    <img src="../../imgs/nginx_logo.png" width="350" height="150"> 
</p>

## Overview

- [Nginx Ingress Controller](#nginx-ingress-controller)
  - [Overview](#overview)
  - [Guides](#guides)
  - [Nginx Ingress](#nginx-ingress)
    - [Nginx Ingress - Deployment](#nginx-ingress---deployment)
    - [Nginx Ingress - Validate](#nginx-ingress---validate)
    - [Nginx Ingress - Clean Up](#nginx-ingress---clean-up)
  - [Nginx Sample App](#nginx-sample-app)
    - [Nginx Sample App - Deployment](#nginx-sample-app---deployment)
    - [Nginx Sample App - Validate](#nginx-sample-app---validate)
    - [Nginx Sample App - Clean Up](#nginx-sample-app---clean-up)

## Guides

* [Nginx Docs - Installation Guide](https://kubernetes.github.io/ingress-nginx/deploy/#quick-start)
* [Spacelift Docs - Kubernetes Ingress with NGINX Ingress Controller Example](https://spacelift.io/blog/kubernetes-ingress)

## Nginx Ingress

### Nginx Ingress - Deployment

```shell 
helm upgrade --install ingress-nginx ingress-nginx \
--repo https://kubernetes.github.io/ingress-nginx \
--namespace ingress-nginx --create-namespace
 ```

### Nginx Ingress - Validate

* ```kubectl get all -n ingress-nginx```

### Nginx Ingress - Clean Up

* ```helm uninstall ingress-nginx -n ingress-nginx```

## Nginx Sample App

### Nginx Sample App - Deployment

* ```kubectl apply -f example-cluster-management/nginx-ingress/sample-nginx-app/manifest.yaml```

### Nginx Sample App - Validate

* ```kubectl ```

### Nginx Sample App - Clean Up

* ```kubectl delete -f example-cluster-management/nginx-ingress/sample-nginx-app/manifest.yaml ```