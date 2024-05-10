# kubectl Commands

A lot of these commands have been pulled from [Sapcelift - Kubectl Cheat Sheet](https://spacelift.io/blog/kubernetes-cheat-sheet#events).

## Environment Management & Context

Checking and setting which environment kubectl is pointing to:

* ```kubectl get all --all-namespaces```
* ```kubectl cluster-info```
* ```kubectl version```
* ```kubectl config view```
* ```kubectl config view -o jsonpath='{.users[*].name}```
* ```kubectl config current-context```
* ```kubectl config get-contexts```
* ```kubectl config use-context docker-desktop``` (or whatever environment you want to use)
* ```kubectl api-resources```
* ```kubectl api-versions```

## Output Format

* ```-o=json, e.g. kubectl get pods -o=json```
* ```-o=yaml, e.g. kubectl get pods -o=yaml```
* ```-o=wide, e.g. kubectl get pods -o=wide```

## Namespaces

* ```-n, e.g. kubectl get pods -n={namespace_name}```

## Configuration Files

### apply

* ```kubectl apply -f {config_file}```
* ```kubectl apply -f {config_file_2} -f {config_file_2}```

### create

* ```kubectl create -f {config_file}```
* ```kubectl create -f {config_file_directory}```
* ```kubectl create -f {url}```

### delete

* ```kubectl delete -f {configuration_file}```

## Deployments

### get

* ```kubectl get deployments```

### edit

* ```kubectl edit deployment {deployment_name}```

### create

* ```kubectl create deployment {deployment_name}```

### delete

* ```kubectl delete deployments {deployment_name}```

### rollout

* ```kubectl rollout status deployment {deployment_name}```
* ```kubectl rollout undo deployment/{deployment_name}```
* ```kubectl rollout restart deployment {deployment_name}```

### replace

* ```kubectl replace --force -f {configuration_file}```

## Pods

* ```kubectl get pod```
* ```kubectl describe pods {pod_name}```
* ```kubectl delete pod {pod_name} ```

## CronJons

### get

* ```kubectl get cronjobs```

### delete

* ```kubectl delete cronjob {cronjob-name}```

## Service Accounts

### get

* ```kubectl get sa```

### describe

* ```kubectl describe sa k8s-password-management-sa```

## Services

### delete

* ```kubectl delete service demo-hello-world-service```

## Logs

* ```kubectl logs {pod_name} -c {container layer} ```

## Container Exec

* ```kubectl exec -it {pod_name} -c {container layer} -- sh```





 



