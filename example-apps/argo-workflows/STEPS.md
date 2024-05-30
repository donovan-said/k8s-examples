# Argo Deployment

<p align="center">
    <img src="../../imgs/argo_logo.png" width="350" height="320"> 
</p>


## Deployment
```shell
ARGO_WORKFLOWS_VERSION="v3.5.7"
kubectl create namespace argo
kubectl apply -n argo -f "https://github.com/argoproj/argo-workflows/releases/download/${ARGO_WORKFLOWS_VERSION}/quick-start-minimal.yaml"
argo submit -n argo --watch https://raw.githubusercontent.com/argoproj/argo-workflows/main/examples/hello-world.yaml
```
## Access Argo

```kubectl -n argo port-forward service/argo-server 2746:2746```
``` https://localhost:2746```

## Clean Up

```kubectl delete -n argo -f "https://github.com/argoproj/argo-workflows/releases/download/${ARGO_WORKFLOWS_VERSION}/quick-start-minimal.yaml```