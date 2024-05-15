# Grafana Deployment

Based on guide by [Anvesh Muppeda - Deploying Nginx on Kubernetes](https://medium.com/@muppedaanvesh/deploying-nginx-on-kubernetes-a-quick-guide-04d533414967)

## Deployment

```shell
kubectl apply -f examples-app/nginx/nginx-namespace.yaml
kubectl apply -f examples-app/nginx/nginx-manifest.yaml -n nginx 
```

## Validate

```shell
kubectl get all -n nginx

or

kubectl get namespaces                    
kubectl get deployments -n nginx 
kubectl get service -n nginx
kubectl get pods -n nginx
kubectl get replicasets -n nginx
```

## Access Grafana

* ```kubectl get all --n nginx ```
* Access nginx in browser via http://localhost:30500/ or http://127.0.0.1:30500/

## Clean Up

```shell
kubectl delete -f examples-app/nginx/nginx-manifest.yaml -n nginx
kubectl delete -f examples-app/nginx/nginx-namespace.yaml
```