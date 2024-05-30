# Nginx Ingress Controller

<p align="center">
    <img src="../../imgs/nginx_logo.png" width="350" height="150"> 
</p>

## Overview

- [Nginx Ingress Controller](#nginx-ingress-controller)
  - [Overview](#overview)
  - [Guides](#guides)
  - [Nginx Ingress - Controller](#nginx-ingress---controller)
    - [Deployment](#deployment)
    - [Validate](#validate)
    - [Clean Up](#clean-up)
  - [Nginx Ingress - Demo Application](#nginx-ingress---demo-application)
    - [Deployment](#deployment-1)
    - [Validate](#validate-1)
      - [CLI](#cli)
      - [Browser](#browser)
    - [Clean Up](#clean-up-1)

## Guides

* [k8s Docs - Set Up Nginx Ingress on Minikube](https://kubernetes.io/docs/tasks/access-application-cluster/ingress-minikube/)
* [Nginx Docs - Installation Guide](https://kubernetes.github.io/ingress-nginx/deploy/#quick-start)
* [Medium - Abdul Gaffoor - Leveraging Ingress, Services, and Deployments](https://itsmegaffoor.medium.com/w-i-p-docker-desktop-kubernetes-deployment-demystified-leveraging-ingress-services-and-6ca828dc2c43)

## Nginx Ingress - Controller

### Deployment

* ```helm upgrade --install ingress-nginx ingress-nginx --repo https://kubernetes.github.io/ingress-nginx --namespace ingress-nginx --create-namespace```

### Validate

* ```kubectl get pods --namespace=ingress-nginx```

### Clean Up

* ```helm uninstall ingress-nginx -n ingress-nginx```

## Nginx Ingress - Demo Application

### Deployment

* ```kubectl apply -f example-cluster-management/nginx-ingress/sample-apps/manifest-ingress-demo.yaml```

### Validate

#### CLI

* ```kubectl port-forward --namespace=ingress-nginx service/ingress-nginx-controller 8080:80```
* ```curl --resolve nginx.demo.local:8080:127.0.0.1 http://nginx.demo.local:8080```

#### Browser

* Add the `nginx.demo.local` record to the /etc/hosts file, see below

```shell
##
# Host Database
#
# localhost is used to configure the loopback interface
# when the system is booting.  Do not change this entry.
##
127.0.0.1       localhost
255.255.255.255 broadcasthost
::1             localhost
# Added by Docker Desktop
# To allow the same kube context to work on the host and the container:
127.0.0.1 kubernetes.docker.internal nginx.demo.local
# End of section
```

### Clean Up

* ```kubectl delete -f example-cluster-management/nginx-ingress/sample-apps/manifest-ingress-demo.yaml```
* Remove entry from /etc/hosts file
