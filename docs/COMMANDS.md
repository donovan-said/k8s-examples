# kubectl Commands

## Environment Management

Checking and setting which environment kubectl is pointing to:

* ```kubectl config get-contexts```
* ```kubectl config use-context docker-desktop``` (or whatever environment you want to use)

## Object Management

### apply

* ```kubectl apply -f manifest.yml```
* ```kubectl apply -f deployment.yaml -f service.yml ```


### get

* ```kubectl get pod -n {namespace}```
* ```kubectl get deployments -n {namespace}```
* ```kubectl get cronjobs -n {namespace}```
* ```kubectl get sa -n {namespace}```

### describe

* ```kubectl describe pods {pod_name} -n {namespace}```
* ```kubectl describe sa k8s-password-management-sa -n {namespace}```

### delete

* ```kubectl delete pod {pod_name} -n {namespace} ```
* ```kubectl delete deployments {deployment_name} -n {namespace}```
* ```kubectl delete service demo-hello-world-service -n {namespace}```
* ```kubectl delete cronjob {cronjob-name}```

### rollout

* ```kubectl rollout restart deployment {deployment_name} -n {namespace}```

### logs

* ```kubectl logs {pod_name} -c {container layer} -n {namespace} ```


## Container Exec

* ```kubectl exec -it {pod_name} -c {container layer} -n {namespace} -- sh```





 



