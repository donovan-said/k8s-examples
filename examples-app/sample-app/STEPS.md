# Sample Hello World App

Based on guides by:

* [Sayed Naweed Rizvi - Setup local Kubernetes cluster with Docker Desktop](https://dev.to/navedrizv/setup-local-kubernetes-cluster-with-docker-desktop-1e7k)
* [Michael Levan - Creating A Kubernetes Service Account ](https://dev.to/thenjdevopsguy/creating-a-kubernetes-service-account-to-run-pods-3ef9)

## Deployment

```shell
kubectl apply -f examples-app/sample-app/sample-namespace.yaml
kubectl apply -f examples-app/sample-app/sample-service-account.yaml -n sample-namespace 
kubectl apply -f examples-app/sample-app/sample-config-map.yaml -n sample-namespace 
kubectl apply -f examples-app/sample-app/sample-secrets.yaml -n sample-namespace 
kubectl apply -f examples-app/sample-app/sample-deployment.yaml -n sample-namespace 
kubectl apply -f examples-app/sample-app/sample-service.yaml -n sample-namespace 
```

## Validate

```shell
kubectl get namespaces 
kubectl get configmaps -n sample-namespace
kubectl get secrets -n sample-namespace
kubectl describe secrets sample-secrete -n sample-namespace                        
kubectl get deployments -n sample-namespace  
kubectl get service -n sample-namespace
kubectl get pods -n sample-namespace 
kubectl get pods -o yaml -n sample-namespace # (validate service account)
```

* Visit: http://localhost:32000/

## Clean Up

```shell
kubectl delete service demo-hello-world-service -n sample-namespace 
kubectl delete deployment demo-hello-world -n sample-namespace 
kubectl delete configmap sample-config -n sample-namespace 
kubectl delete secret sample-secrete -n sample-namespace 
kubectl delete namespace sample-namespace
```