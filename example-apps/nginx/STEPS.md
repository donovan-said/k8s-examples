# Nginx Deployment

Based on guide by 

## Deployment

* ```kubectl apply -f example-apps/nginx/nginx-manifest.yaml -n nginx```

## Validate

* ```kubectl get all -n nginx```

or

* ```kubectl get namespaces```             
* ```kubectl get deployments -n nginx```
* ```kubectl get service -n nginx```
* ```kubectl get pods -n nginx```
* ```kubectl get replicasets -n nginx```

## Access Nginx

* ```kubectl get all --n nginx ```
* Access nginx in browser via http://localhost:30500/ or http://127.0.0.1:30500/

## Clean Up

```kubectl delete -f example-apps/nginx/nginx-manifest.yaml -n nginx```



curl --resolve "nginx-hello.info:80:127.0.0.1" -i http://nginx-hello.info