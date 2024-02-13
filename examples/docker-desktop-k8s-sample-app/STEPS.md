# Sample Hello World App

Based on guide by [Sayed Naweed Rizvi - Setup local Kubernetes cluster with Docker Desktop](https://dev.to/navedrizv/setup-local-kubernetes-cluster-with-docker-desktop-1e7k)

## Deployment

```shell
kubectl apply -f deployment.yml
kubectl get deployments
kubectl get pods
kubectl apply -f service.yml
kubectl get service
```

## Clean Up

```shell
kubectl delete service demo-hello-world-service 
kubectl delete deployment demo-hello-world 
```