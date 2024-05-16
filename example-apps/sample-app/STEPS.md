# Sample Hello World App

Based on guides by:

* [Sayed Naweed Rizvi - Setup local Kubernetes cluster with Docker Desktop](https://dev.to/navedrizv/setup-local-kubernetes-cluster-with-docker-desktop-1e7k)
* [Michael Levan - Creating A Kubernetes Service Account ](https://dev.to/thenjdevopsguy/creating-a-kubernetes-service-account-to-run-pods-3ef9)

## Deployment

* ```kubectl apply -f example-apps/sample-app/sample-app-manifest.yaml -n sample-namespace```

## Validate

* ```kubectl get namespaces```
* ```kubectl get configmaps -n sample-namespace```
* ```kubectl get secrets -n sample-namespace```
* ```kubectl describe secrets sample-secrete -n sample-namespace```                      
* ```kubectl get deployments -n sample-namespace```
* ```kubectl get service -n sample-namespace```
* ```kubectl get pods -n sample-namespace```
* ```kubectl get pods -o yaml -n sample-namespace # (validate service account)```

* Visit: http://localhost:32000/

## Clean Up

* ```kubectl delete -f example-apps/sample-app/sample-app-manifest.yaml -n sample-namespace```