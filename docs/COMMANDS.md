# kubectl Commands

A lot of these commands have been pulled from [Sapcelift - Kubectl Cheat Sheet](https://spacelift.io/blog/kubernetes-cheat-sheet#events).

- [kubectl Commands](#kubectl-commands)
  - [Output Format \& General Options](#output-format--general-options)
  - [Configuration Files (Manifests)](#configuration-files-manifests)
  - [Cluster Management \& Context](#cluster-management--context)
  - [Proxy](#proxy)
  - [Cronjobs](#cronjobs)
  - [DaemonSets](#daemonsets)
  - [Deployments](#deployments)
  - [Events](#events)
  - [Logs](#logs)
  - [Nodes](#nodes)
  - [Namespaces](#namespaces)
  - [Pods](#pods)
  - [ReplicaSets](#replicasets)
  - [Roles \& Role Bondings](#roles--role-bondings)
  - [Secrets](#secrets)
  - [Services](#services)
  - [Service Accounts](#service-accounts)

## Output Format & General Options

* ```alias k=kubectl```
* ```-o=json, e.g. kubectl get pods -o=json```
* ```-o=yaml, e.g. kubectl get pods -o=yaml```
* ```-o=wide, e.g. kubectl get pods -o=wide```
* ```-n, e.g. kubectl get pods -n={namespace_name}```

## Configuration Files (Manifests)

* ```kubectl --kubeconfig=path/to/kubeconfig {some_command}```
* ```kubectl apply -f {config_file}```
* ```kubectl apply -f {config_file_2} -f {config_file_2}```
* ```kubectl create -f {config_file}```
* ```kubectl create -f {config_file_directory}```
* ```kubectl create -f {url}```
* ```kubectl delete -f {configuration_file}```
  
## Cluster Management & Context

Checking and setting which environment kubectl is pointing to:

* ```kubectl explain {object_type}```
* ```kubectl get all --all-namespaces```
* ```kubectl cluster-info```
* ```kubectl version```
* ```kubectl config view```
* ```kubectl config view -o jsonpath='{.users[*].name}```
* ```kubectl config current-context```
* ```kubectl config get-contexts```
* ```kubectl config use-context docker-desktop``` (or whatever environment you want to use)
* ```kubectl api-resources``` (A list of all object types: name, shortname, api version, namespaced, kind)
* ```kubectl api-versions``` (A list of all object type api versions)
* ```kubectl get configmaps```
* ```kubectl describe configmap {configmap_name}```
* ```kubectl get configmap {configmap_name} -o jsonpath='{.data}' | jq``` (Get ConfigMap JSON object)
* ```kubectl delete configmap {configmap_name}```

## Proxy

* ```kubectl proxy```

## Cronjobs

* ```kubectl get cronjobs```
* ```kubectl delete cronjob {cronjob_name}```

## DaemonSets

* ```kubectl get daemonset```
* ```kubectl edit daemonset {daemonset_name}```
* ```kubectl delete daemonset {daemonset_name}```
* ```kubectl create daemonset {daemonset_name}```
* ```kubectl rollout daemonset```
* ```kubectl describe ds {daemonset_name} -n {namespace_name}```

## Deployments

* ```kubectl get deployments```
* ```kubectl edit deployment {deployment_name}```
* ```kubectl create deployment {deployment_name}```
* ```kubectl delete deployments {deployment_name}```
* ```kubectl rollout status deployment {deployment_name}```
* ```kubectl rollout undo deployment/{deployment_name}```
* ```kubectl rollout restart deployment {deployment_name}```
* ```kubectl replace --force -f {configuration_file}```

## Events

* ```kubectl get events```
* ```kubectl get events --field-selector type=Warning```
* ```kubectl get events --sort-by=.metadata.creationTimestamp```
* ```kubectl get events --field-selector involvedObject.kind!=Pod```
* ```kubectl get events --field-selector involvedObject.kind=Node, involvedObject.name={node_name}```
* ```kubectl get events --field-selector type!=Normal```

## Logs

* ```kubectl logs {pod_name}```
* ```kubectl logs --since=6h {pod_name}```
* ```kubectl logs --tail=50 {pod_name}```
* ```kubectl logs -f {service_name} [-c <$container>]```
* ```kubectl logs -f {pod_name}```
* ```kubectl logs -c {container_name} {pod_name} ```
* ```kubectl logs {pod_name} pod.log```
* ```kubectl logs --previous <pod_name>```

## Nodes

* ```kubectl taint node {node_name}```
* ```kubectl get node```
* ```kubectl delete node {node_name}```
* ```kubectl top node {node_name}```
* ```kubectl get pods -o wide | grep {node_name}```
* ```kubectl annotate node {node_name}```
* ```kubectl cordon node {node_name}```
* ```kubectl uncordon node {node_name}```
* ```kubectl drain node {node_name}```
* ```kubectl label node```

## Namespaces

* ```kubectl create namespace {namespace_name}```
* ```kubectl get namespace {namespace_name}```
* ```kubectl describe namespace {namespace_name}```
* ```kubectl delete namespace {namespace_name}```
* ```kubectl edit namespace {namespace_name}```
* ```kubectl top namespace {namespace_name}```

## Pods

* ```kubectl get pod```
* ```kubectl get pods --sort-by='.status.containerStatuses[0].restartCount```
* ```kubectl get pods --field-selector=status.phase=Running```
* ```kubectl delete pod {pod_name}```
* ```kubectl describe pod {pod_name}```
* ```kubectl create pod {pod_name}```
* ```kubectl exec {pod_name} -c <container_name> <command>```
* ```kubectl exec -it {pod_name} /bin/sh```
* ```kubectl top pod```
* ```kubectl annotate pod {pod_name} <annotation>```
* ```kubectl label pods {pod_name} new-label=<label name>```
* ```kubectl get pods --show-labels```
* ```kubectl port-forward {pod_name} <port number to listen on>:<port number to forward to>```

## ReplicaSets

* ```kubectl get replicasets```
* ```kubectl describe replicasets {replicaset_name}```
* ```kubectl kubectl scale --replicas=[x]```

## Roles & Role Bondings

* ```kubectl get clusterroles```
* ```kubectl describe clusterroles```
* ```kubectl get clusterrolebindings```
* ```kubectl describe clusterrolebindings```
* ```kubectl get roles```
* ```kubectl describe roles```
* ```kubectl get rolebindings```
* ```kubectl describe rolebindings```

## Secrets

* ```kubectl create secret```
* ```kubectl get secrets```
* ```kubectl describe secrets```
* ```kubectl delete secret {secret_name}```

## Services

* ```kubectl get services```
* ```kubectl kubectl describe services```
* ```kubectl expose deployment [deployment_name]```
* ```kubectl edit services```

## Service Accounts

* ```kubectl get serviceaccounts```
* ```kubectl describe serviceaccounts```
* ```kubectl replace serviceaccount```
* ```kubectl delete serviceaccount {service_account_name}```




 



